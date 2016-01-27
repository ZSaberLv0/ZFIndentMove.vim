# ZFIndentMove.vim

vim script to move cursor quickly accorrding indent


# how to use

1. use [Vundle](https://github.com/VundleVim/Vundle.vim) or any other plugin manager you like to install

    ```
    Plugin 'ZSaberLv0/ZFIndentMove.vim'
    ```

1. have your own keymap in your vimrc, recommended keymap:

    ```
    nnoremap EE ``
    nnoremap EH :call ZF_IndentMoveParent()<cr>
    nnoremap EL :call ZF_IndentMoveChild()<cr>
    nnoremap EK :call ZF_IndentMovePrev()<cr>
    nnoremap EJ :call ZF_IndentMoveNext()<cr>
    ```

# functions

* `ZF_IndentGetIndentLevel(line)`

    get indent level of line, accorrding to your `tabstop`

* `ZF_IndentIsEmpty(line)`

    true if line is empty or contains spaces or tabs only

* `ZF_IndentMoveParent()`

    move up to nearest parent indent
    (whose indent is less than current line)

    ```
    move >> foo
                foo

     cur >>     foo
    ```

* `ZF_IndentMoveParentEnd()`

    move down to nearest parent indent
    (whose indent is less than current line)

    ```
     cur >>     foo

                foo
    move >> foo
    ```

* `ZF_IndentMoveChild()`

    move down to nearest child indent
    (whose indent is larger than current line)

    ```
     cur >> foo
            foo

    move >>     foo
    ```

* `ZF_IndentMovePrev()`

    move up to nearest sibling or parent indent
    (whose indent is equal to or less than current line, skip first empty or same indent line)

    ```
    move >> foo

            foo
     cur >> foo
    ```

    or

    ```
    move >> foo
                foo
     cur >>     foo
    ```

* `ZF_IndentMoveNext()`

    move down to nearest sibling or parent indent
    (whose indent is equal to or less than current line, skip first empty or same indent line)

    ```
     cur >> foo
            foo

    move >> foo
    ```

    or

    ```
     cur >>     foo
                foo
    move >> foo
    ```

