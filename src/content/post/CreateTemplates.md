---
title: "Create and use templates in Linux"
description: "In this post we shall look into how to create templates and use them to create a document from the terminal itself"
publishDate: "15 May 2024"
tags: ["linux", "templates"]
author: Suraj Kumar Panigrahi
---
## But why create templates?
There are a lot of types of files that we use very frequently. For instance, someone like me who loves to analyse chess games would require to create .pgn files very frequently. If you code in C++ or C or if you work in Latex like me you'd need to create such files with the headers again and again, this indeed is a pain in the **A**. 

## Creating a Template

Let's first open the terminal ( <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>t</kbd> ) and go the the ~/Templates directory 
```zsh
suajkp@nutrino:~ $ cd ~/Templates
```
create a blank document in the format **"<file_extension>.template"** , ( _here, I will be doing for .pgn - Portable Game Notation_ ), and open it with your favourite texteditor. I'd use neovim for instance.
```zsh
suajkp@nutrino:~/Templates $ touch pgn.template
suajkp@nutrino:~/Templates $ nvim pgn.template
```
Now, this is the part where you'd like to differ from me. Write whatever you think you need to be there in the template.

```pgn
[Event "?"]
[Site "?"]
[Date "????.??.??"]
[Round "?"]
[White "?"]
[Black "?"]
[Result "*"]

1.e4 e5 {This is how to write the moves and add commentary to the game in curled braces}

```
Save and quit neovim <kbd>ESC</kbd>, <kbd>:wq</kbd>.
Now we have a template for .pgn files. And you may do the same for other file types that you use frequently.

## Problem in hand right now

Since we have created templates for our files, we'd expect the task been done. Actually it's a yes and a no. By yes I mean if you use GUI all the time (in this case you are a disgrace to Linux community), then all you have to do is go to any directory where you want to create a document using the templates we just created, do right click, hover over new document, and the templates will appar infront of you. But if you are in the greener and more fancier side of the fence, then there we have some work to do since the template feature is not native to vanila linux, it is a functionality provided by the Desktop environment (which by definition is GUI).

## Editing .bashrc or .zshrc is the SOLUTION

In this section we intend to create a function that takes the file name you want to create as parameter and check the extension type to decide which template to be used.

Again open your .zshrc (or .bashrc). 
```sh
suajkp@nutrino: ~$ nvim .zshrc
```
And scroll down to where you write your personal aliases (Technically you can write any where you wish but let's keep our business clean) and paste the following code.

```sh
# Function for creating document form templates.
temptouch(){
   # Get the filename and extension
  filename="$1"
  extension="${filename##*.}"

  # Check if file already exists (optional)
  if [ -f "$filename" ]; then
    echo "File '$filename' already exists. Skipping creation."
    return 1
  fi

  # Check if template exists for the extension
  template_file="$HOME/Templates/${extension}.template"
  if [ -f "$template_file" ]; then
    # Copy template and replace ".template" with filename
    cp "$template_file" "$filename"
    echo "Document created from template: $template_file"
  else
    echo "No template found for file type: .$extension"
  fi 
}
```
Now <kbd>ESC</kbd> and <kbd>:wq<kbd> to save and quit neovim. 

Now you can use it as:
```sh
suajkp@nutrino:~/Documents/MyGames $ temptouch Anand_vs_Inkiov_1986.pgn
```
And you are ready to go 

: )


