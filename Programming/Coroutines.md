A routine that runs concurrently with other coroutines. Coroutines do not necessarily run in parallel. A coroutine can temporarily relinguish control to another coroutine without involving the subroutine calling mechanism. That is, control in a coroutine can jump to another coroutine and back, possibly multiple times during the lifetime of a coroutine. Therefore, it appears as if the coroutines are operating concurrently.