# Plugins

## Autocomplete

### References

Plugin

<https://www.vim.org/scripts/script.php?script_id=1879>

Download zip

<https://www.vim.org/scripts/download_script.php?src_id=11894>

### Steps

1. Extract zip content.

2. Move all extracted files and folders to a path  of the Vim's runtimepath.

    Show runtime paths
    
    ```bash
    :set runtimepath?
    ```
      
    Copy files example:
      
    ```bash
    # Create folder if not exists.
    mkdir ~/.vim
    # Copy files.
    cp -r Descargas/vim-autocomplpop/* .vim
    ```

3. If it does not work try restarting your host or virtualmachine (is not necesary active the fuzzyhelp).
