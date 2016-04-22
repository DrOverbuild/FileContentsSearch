# FileContentsSearch
A Java command-line program that recursively searches all text files for a given string in a given directory.

This tool searches through all text files within a given directory for given matches. It goes though all
directories in the given directory as well. To use this, command-line arguments must be set. If you want to
search in the current working directory, simply list only the matches you're searching for. If you want to
search in a different directory, the first argument must start with "-dir:" with the path following. If the
path has spaces in it, precede each space with a backslash (\). After that, list the matches. To show help,
the first argument must be "---help".

This tool is non-case sensitive, meaning that it will ignore the cases of searches. So if a text file contains
"Hello!" and the match given is "hello", then "Hello!" will be listed. If a desired match contains several
words, surround these with double quotation marks ("). For example, to search for "good bye", the command would
look like this:

`java -jar FCS.jar -dir:<dir> "good bye"`

If you want to ignore some text, precede the text with two dashes (--). Any line containing this in the given
text files will not be listed in the output. In addition, quotation marks can also be used if the match to
ignore has more than one word. For example, to list any line that contains "Hello" but not "Hello World!", the
command would look like this:

`java -jar FCS.jar -dir:<dir> Hello --"Hello World!"`

Here are some more examples of ways to use this:

`java -jar FCS.jar hi! --hello "good day"` will list lines containing "hi!", and "good day" unless the line
contains "hello"