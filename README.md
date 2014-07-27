# NAME

PDF::Tk - Perl integration for the pdf toolkit (pdftk)

# SYNOPSIS

    use PDF::Tk;
    my $doc=PDF::Tk->new(file=>["/tmp/my1.pdf","/tmp/my2.pdf"]);
    my @parts=$doc->pages();

# DESCRIPTION

This module is a interface for the command line pdftk command. 

# METHODS

- new

    The constructor for the pdftk module. Takes a hash of arguments

        document - a scalar containing a PDF document,
        file - either a PDF filename or a arrayref of filenames.
        pdftf - path to the pdftk binary, defaults to searching $PATH

    note that document and file are mutually exclusive!

- call\_pdftk

    Calls up pdftk command, takes input, output and pdftk operation as arguments
    input and output can either be files or scalar refs. input can also be an
    array ref of files

- pages

    returns an array in list context, or arrayref, containing the content of all
    pages in the document.

- page

    Takes a page as an argument, and returns the contents of that page.

- docinfo

    If you provide an argument, it will return that value (lower cased), or 
    else it will return a hash of values;
    Common values are **creator** ,**title**, **producer**,**author**, **moddate**,
    **creationdate**, **pdfid0**, **pdfid1**, **numberofpages**.

- document

    Accessor for the actual document.

# SEE ALSO

[http://www.accesspdf.com/pdftk/](http://www.accesspdf.com/pdftk/)

# AUTHOR

Marcus Ramberg, <marcus@mediaflex.no>

# COPYRIGHT AND LICENSE

Copyright 2004 by Mediaflex A/S.

This library is free software; you can redistribute it and/or modify
it under the same terms as Perl itself. 
