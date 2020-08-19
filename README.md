# rc double quotes fork

Hi, this is my fork of Byron Rakitzis' implementation of rc, the Plan 9 shell:
github.com/rakitzis/rc. While I don't use rc anymore, I originally made this to
support a feature of BASH that I really liked that rc lacked which was double
quotes.

Double quotes work pretty much the same way as single quotes except that
you can use shell variables within them. There are other features and aspects of
double quotes that exist in BASH but I chose not to implement them. This
modification allows the user to access BASH environment variables like $HOME
while preventing rc from tokenizing it by separated white space (spaces and
newlines).

## EXAMPLE

Original:
  cmd: echo "This is my home directory: $HOME"
  argv: {"/bin/echo", "\"This", "is", "my", "home", "directory:", "/home/paul\""};

Dquotes:
  cmd: echo "This is my home directory: $HOME"
  argv: {"/bin/echo", "This is my home directory: /home/paul"};
