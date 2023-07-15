# first swift app 

## purpose

Built your first app using the terminal.

## prepare

check tools:

```bash
swift --version
```

## steps

1. create a folder for the project (optional)
    * the name of the folder is `HelloSwift`

    ```bash
    mkdir HelloSwift
    cd HelloSwift
    ```

2. init

    ```bash
    swift package init --type executable
    ```

3. run your project

    ```bash
    swift run
    ```

    expected output:

    ```bash
    Hello, World!
    ```

## test

1. open your project(name: HelloSwift) in Xcode

2. find the `main.swift` in `Sources`

3. edit the content and then save it(command + `s`)

    from:

    ```swift
    print("Hello, World!")
    ```

    to:
    ```swift
    print("Hello, Swift!")
    ```

4. go back to the terminal and run your project again

    ```bash
    swift run
    ```

    expected output:

    ```bash
    Hello, Swift!
    ```
 
 ## reference

 1. https://www.swift.org/getting-started
