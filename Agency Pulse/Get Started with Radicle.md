1.  Install the Radicle `rad` CLI.
    
    👉 To install with **🍺 Homebrew**, run:
    
    brew tap radicle/cli https://seed.alt-clients.radicle.xyz/radicle-cli-homebrew.git
    brew install radicle-cli
    
    👉 To install on 🐧 **Debian/Ubuntu**, first download the package signing key:
    
    curl https://europe-west6-apt.pkg.dev/doc/repo-signing-key.gpg | sudo apt-key add -
    
    Then update your sources list with the radicle repository by creating a registry file:
    
    echo deb https://europe-west6-apt.pkg.dev/projects/radicle-services radicle-cli main | sudo tee -a /etc/apt/sources.list.d/radicle-registry.list
    
    Then update the package list and install `radicle-cli`:
    
    sudo apt update
    sudo apt install radicle-cli
    
2.  Run `rad auth` to create your Radicle identity.
    
    The first time you run `rad auth`, you are prompted to create a new radicle identity and Ed25519 keypair.
    
    $ rad auth
    Initializing your 🌱 profile and identity
    
    ok Username · koops
    ok Passphrase · ********
    ok Creating your 🌱 Ed25519 keypair...
    ok Adding to ssh-agent...
    ok Profile 3ae66df3-6ac7-4466-9013-83839749ed05 created.
    
    Your radicle Peer ID is hyncoz7x4s8x9447g6yogy4iy41q8i4juy5uhou57w1ga7obt644wo. This identifies your device.
    Your personal 🌱 URN is rad:git:hnrkmx6trm4bu19bwa4apbxj8ftw8f7amfdyy. This identifies you across devices.
    
    => To create a radicle project, run `rad init` from a git repository.
    
3.  Navigate to an existing **git repository** on your device.
    
    Radicle is built around git.
    
    $ cd acme
    
4.  Run `rad init` to create a Radicle **project** from the repo.
    
    This creates a **unique peer-to-peer identity** for your repository that can be shared on the network, and associates your radicle key with it.
    
    $ rad init
    Initializing local 🌱 project acme
    
    ok Description · The Acme Corporation is an ironic name for the fictional corporation
    ok Default branch · main
    ok Initializing new project...
    ok Project initialized: rad:git:hnrkqi6ohci9m59i54ppiy3fqkedkjt98ymdo
    
    => To publish, run `rad push`.
    
5.  Run `rad push` to publish to the network.
    
    The first time you push, you will be asked to select a seed node to push to. To push to your own seed, specify its address with the `--seed` option.
    
    $ rad push
    Pushing 🌱 to remote `rad`
    Everything up-to-date
    
    Git version 2.35.1
    Select a seed node to sync with...
    * pine.radicle.garden
    * willow.radicle.garden
    * maple.radicle.garden
    
    Your code will be synced and available on the network via the web or git.
    
    Git signing key ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIL460KIEccS4881p7PPpiiQBsxF+H5tgC6De6crw9rbU
    
    Syncing 🌱 project rad:git:hnrkqi6ohci9m59i54ppiy3fqkedkjt98ymdo to https://willow.radicle.garden
    
    ok Syncing delegate identity hnrkqdpm9ub19oc8dccx44echy76hzfsezyio...
    ok Syncing project identity...
    ok Syncing project refs...
    ok Fetching remotes (*)...
    ok Project synced.
    
    🌱 Your project is synced and available at:
    
        (web) https://app.radicle.xyz/seeds/willow.radicle.garden/rad:git:hnrkqi6ohci9m59i54ppiy3fqkedkjt98ymdo/
        (git) https://willow.radicle.garden/hnrkqi6ohci9m59i54ppiy3fqkedkjt98ymdo.git
    
6.  Share your project with friends.
    
    Anyone can clone your project via `rad clone` given the project **URN** and a **seed** to clone from. To clone the above project, run:
    
    $ rad clone rad:git:hnrkqi6ohci9m59i54ppiy3fqkedkjt98ymdo --seed willow.radicle.garden
    
    Git version 2.35.1
    
    Syncing 🌱 project rad:git:hnrkqi6ohci9m59i54ppiy3fqkedkjt98ymdo from https://willow.radicle.garden/
    
    ok Fetching project identity...
    ok Fetching project delegate hnrkqdpm9ub19oc8dccx44echy76hzfsezyio...
    ok Verifying...
    ok Fetching default remotes...
    
    Initializing local checkout for 🌱 rad:git:hnrkqi6ohci9m59i54ppiy3fqkedkjt98ymdo (acme)
    
    ok Local master branch found...
    ok Performing checkout...
    ok Remote-tracking branch koops/main created for hyn9diw…zo645pe
    ok Local repository seed for acme set to https://willow.radicle.garden/
    ok Tracking for project delegates configured
    
    🌱 Project clone successful under ./acme
                
    
7.  All set 🌱
    
    Run `rad help` to see what additional commands are available.
    
    Usage: rad  [--help]
    Common `rad` commands used in various situations:
    
        **auth**         Manage radicle identities and profiles
        **init**         Initialize radicle projects from git repositories
        **self**         Show information about your radicle identity and device
        **clone**        Clone radicle projects
        **ls**           List radicle projects and other objects
        **remote**       Manage radicle remotes
        **push**         Publish radicle projects to the network
        **pull**         Pull radicle project refs into a working copy
        **checkout**     Checkout a radicle project working copy
        **track**        Manage radicle project tracking relationships
        **untrack**      Untrack radicle project peers
        **sync**         Synchronize radicle projects with seeds
        **ens**          Manage your radicle ENS records
        **help**         Radicle CLI help
    
    See `rad  --help` to learn about a specific command.