# The authenticity of host 'github.com (20.27.177.113)' can't be established

## expectation

connect to `github.com` successfully

## description

I opened Terminal and entered the command `git clone git@github.com:LPenny-github/Notes2307.git`. It failed with the warning message: The authenticity of host 'github.com (20.27.177.113)' can't be established. ED25519 key fingerprint is SHA256:+DiY3wvvV6TuJJhbpZisF/zLDA0zPMSvHdkr4UvCOqU.
This key is not known by any other names. Are you sure you want to continue connecting (yes/no/[fingerprint])?

## what & why

1. `ssh` is a way to communicate like `https`.

1. `https` has a middle organization to verify the server for user, but `ssh` doesn't have.

1. When using `ssh`, user has to verify if the the server is truly what it is.

1. The way to verify a server is to check out its fingerprint and public key in your `~/.ssh/known_hosts` file.

## how

1. check your `~/.ssh/known_hosts` file

    ```bash
    ls ~/.ssh
    ```
        
    * `ls` <folder path>: list all files in this folder

    my case(output) is:

    ```No such file or directory```

1. create your `~/.ssh/known_hosts` file. there are at least three ways:

    * github's fingerprints list on its official docs:
        * GitHub's SSH key fingerprints
            * https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/githubs-ssh-key-fingerprints

            ```text
            SHA256:uNiVztksCsDhcc0u9e8BujQXVUpKZIDTMczCvj3tD2s (RSA)
            SHA256:br9IjFspm1vxR3iA35FWE+4VTyz1hYVLIE2t1/CeyWQ (DSA - deprecated)
            SHA256:p2QAMXNIC1TJYWeIOttrVc98/R1BUFWu3/LiyKgUfQM (ECDSA)
            SHA256:+DiY3wvvV6TuJJhbpZisF/zLDA0zPMSvHdkr4UvCOqU (Ed25519)
            ```


    * (1) Type `git clone git@github.com:LPenny-github/Notes2307.git`. As it shows warnning message, check out the code of fingerprint and then enter `yes`.

        ```
        The authenticity of host 'github.com (20.27.177.113)' can't be established. ED25519 key fingerprint is SHA256:+DiY3wvvV6TuJJhbpZisF/zLDA0zPMSvHdkr4UvCOqU.
        This key is not known by any other names. Are you sure you want to continue connecting (yes/no/[fingerprint])?
        ```

    * (2) type `ssh -T git@github.com`. As it shows warnning message, check out the code of fingerprint and enter `yes`.

        warning message:

        ```
        The authenticity of host 'github.com (20.27.177.113)' can't be established.
        ED25519 key fingerprint is SHA256:+DiY3wvvV6TuJJhbpZisF/zLDA0zPMSvHdkr4UvCOqU.
        This key is not known by any other names
        Are you sure you want to continue connecting (yes/no/[fingerprint])?
        ```

    * (3) create the file manually.

## test

open Terminal:

```bash
cat ~/.ssh/known_hosts
```

my expected output:

```bash
github.com ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIOMqqnkVzrm0SdG6UOoqKLsabgH5C9okWi0dh2l9GKJl
```

your expected output should be at least one of them:

```bash
github.com ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIOMqqnkVzrm0SdG6UOoqKLsabgH5C9okWi0dh2l9GKJl
github.com ecdsa-sha2-nistp256 AAAAE2VjZHNhLXNoYTItbmlzdHAyNTYAAAAIbmlzdHAyNTYAAABBBEmKSENjQEezOmxkZMy7opKgwFB9nkt5YRrYMjNuG5N87uRgg6CLrbo5wAdT/y6v0mKV0U2w0WZ2YB/++Tpockg=
github.com ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABgQCj7ndNxQowgcQnjshcLrqPEiiphnt+VTTvDP6mHBL9j1aNUkY4Ue1gvwnGLVlOhGeYrnZaMgRK6+PKCUXaDbC7qtbW8gIkhL7aGCsOr/C56SJMy/BCZfxd1nWzAOxSDPgVsmerOBYfNqltV9/hWCqBywINIR+5dIg6JTJ72pcEpEjcYgXkE2YEFXV1JHnsKgbLWNlhScqb2UmyRkQyytRLtL+38TGxkxCflmO+5Z8CSSNY7GidjMIZ7Q4zMjA2n1nGrlTDkzwDCsw+wqFPGQA179cnfGWOWRVruj16z6XyvxvjJwbz0wQZ75XK5tKSb7FNyeIEs4TT4jk+S4dhPeAUC5y+bDYirYgM4GC7uEnztnZyaVWQ7B381AK4Qdrwt51ZqExKbQpTUNn+EjqoTwvqNj4kqx5QUCI0ThS/YkOxJCXmPUWZbhjpCg56i+2aB6CmK2JGhn57K5mj0MNdBXA4/WnwH6XoPWJzK5Nyu2zB3nAZp+S5hpQs+p1vN1/wsjk=
```


## reference

* Testing your SSH connection
    * https://docs.github.com/en/enterprise-cloud@latest/authentication/connecting-to-github-with-ssh/testing-your-ssh-connection

* Checking for existing SSH keys
    * https://docs.github.com/en/authentication/connecting-to-github-with-ssh/checking-for-existing-ssh-keys#checking-for-existing-ssh-keys

* GitHub's SSH key fingerprints
    * https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/githubs-ssh-key-fingerprints



