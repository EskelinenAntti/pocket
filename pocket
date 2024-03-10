#!/usr/bin/env bash

POCKET_HOME="$HOME/.pocket"

function pocket_add() {
    if [ -z "$1" ] || [ "$1" = "--help" ] || [ "$1" = "-h" ]; then
        echo 'Write down new commands.'
        echo ''
        echo 'Usage: pocket add "git restore origin --source origin/main myfile.txt"'
        return
    fi

    echo $1 >>$POCKET_HOME
    pocket_clean_up
}

function pocket_find() {
    if [ -z "$1" ] || [ "$1" = "--help" ] || [ "$1" = "-h" ]; then
        echo 'Find commands with a query (the 'query' can be a regural expression)'
        echo ''
        echo 'Usage: pocket find "restore"'
        return
    fi

    grep $1 $POCKET_HOME
}

function pocket_list() {
    if [ "$1" = "--help" ] || [ "$1" = "-h" ]; then
        echo "List all the commands you've saved."
        echo ''
        echo 'Usage: pocket list'
        return
    fi

    less $POCKET_HOME
}

function pocket_edit() {
    if [ "$1" = "--help" ] || [ "$1" = "-h" ]; then
        echo 'Edit the saved commands. Opens a text editor.'
        echo ''
        echo 'Usage: pocket edit'
        return
    fi
    vim $POCKET_HOME
    pocket_clean_up
}

function pocket_clean_up() {
    local temp_pocket_home="$POCKET_HOME-temp"
    sort -o $POCKET_HOME $POCKET_HOME
    sed '/^$/d' $POCKET_HOME >$temp_pocket_home
    mv $temp_pocket_home $POCKET_HOME
}

touch $POCKET_HOME

if [ "$1" = "--help" ] || [ "$1" = "-h" ]; then
    echo "Usage: pocket add|find|list|edit"
    return
fi

case $1 in
add)
    pocket_add $2
    ;;
find)
    pocket_find $2
    ;;
list)
    pocket_list $2
    ;;
edit)
    pocket_edit $2
    ;;
*)
    echo "Usage: pocket add|find|list|edit"
    ;;
esac
