A [[top-down parser]][![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#topdownparser) based on recursive functions.

Consider for example, the following LL(1) grammar

<_expr_> -> <_term_> <_term_tail_>

<_term_tail_> -> <_add_op_> <_term_> <_term_tail_> | e

<_term_> -> <_factor_> <_factor_tail_>

<_factor_tail_> -> <_mult_op_> <_factor_> <_factor_tail_> | e

<_factor_> -> ( <_expr_> ) | - <_factor_> | identifier | unsigned_integer

<_add_op_> -> + | -

_<mult_op> -> * | /_

For this LL(1) grammar a recursive descent [[parser]] in [[Java]] is:

import java.io.*;
public class CalcParser
{ private static StreamTokenizer tokens;
  private static int ahead;
  public static void main(String argv[]) throws IOException
  { InputStreamReader reader = new InputStreamReader(System.in);
    tokens = new StreamTokenizer(reader);
    tokens.ordinaryChar('.');
    tokens.ordinaryChar('-');
    tokens.ordinaryChar('/');
    get();
    expr();
    if (ahead == (int)'$')
      System.out.println("Syntax ok");
    else
      System.out.println("Syntax error");
  }
  private static void get() throws IOException
  { ahead = tokens.nextToken();
  }
  private static void expr() throws IOException
  { term();
    term_tail();
  }
  private static void term_tail() throws IOException
  { if (ahead == (int)'+' || ahead == (int)'-')
    { add_op();
      term();
      term_tail();
    }
  }
  private static void term() throws IOException
  { factor();
    factor_tail();
  }
  private static void factor_tail() throws IOException
  { if (ahead == (int)'*' || ahead == (int)'/')
    { mult_op();
      factor();
      factor_tail();
    }
  }
  private static void factor() throws IOException
  { if (ahead == (int)'(')
    { get();
      expr();
      if (ahead == (int)')')
        get();
      else System.out.println("closing ) expected");
    }
    else if (ahead == (int)'-')
    { get();
      factor();
    }
    else if (ahead == tokens.TT_WORD)
      get();
    else if (ahead == tokens.TT_NUMBER)
      get();
    else System.out.println("factor expected");
  }
  private static void add_op() throws IOException
  { if (ahead == (int)'+' || ahead == (int)'-')
      get();
  }
  private static void mult_op() throws IOException
  { if (ahead == (int)'*' || ahead == (int)'/')
      get();
  }
}

[Get Java source](https://www.cs.fsu.edu/~engelen/courses/COP402003/CalcParser.java).This parser does not construct a parse tree but verifies if a string terminated with a $ is an expression.