# ZFIndentMove.vim

vim script to move cursor quickly accorrding indent


# how to use

1. use [Vundle](https://github.com/VundleVim/Vundle.vim) or any other plugin manager you like to install

    ```
    Plugin 'ZSaberLv0/ZFIndentMove.vim'
    ```

1. have your own keymap in your vimrc

    ```
    nnoremap QH :call ZF_IndentMoveParent()<cr>
    nnoremap QL :call ZF_IndentMoveParentEnd()<cr>
    nnoremap QK :call ZF_IndentMovePrev()<cr>
    nnoremap QJ :call ZF_IndentMoveNext()<cr>
    ```

# example

assume you have something like this

```
         void func()
  QH >>  {
             foo();
QKQK >>      foo();

             foo();
  QK >>      foo();

             foo();
 cur >>      foo();
             foo();

  QJ >>      foo();
             foo();

QJQJ >>      foo();
             foo();
  QL >>  }
```
