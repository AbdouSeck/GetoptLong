This package wraps the powerful Perl module `Getopt::Long` and keeps almost all
features of it. The syntax of option specification is as same as `Getopt::Long`.
So if you are coming from Perl and you know `Getopt::Long`, it would be no
difficulty in using it. This package supports default values, imports option
names into working environment, and automatically generates help messages.
The usage is very simple:

    library(GetoptLong)
    cutoff = 0.05
    GetoptLong(c(
        "cutoff=f",  "cutoff of something (default is 0.05)",
        "input=s",   "input file",
        "verbose=!", "print messages"
    ))
    
Then you can run this script by:

    Rscript foo.R --cutoff 0.01 --input foo.txt --verbose
    Rscript foo.R -i foo.txt -v
    Rscript foo.R -i foo.txt --no-verbose
    
This package also supports simple variable interpolation in R, which means you
can embed variables into texts directly, just like in Perl.

    r = c(1, 2)
    value = 4
    name = "name"
    qq("region = (@{r[1]}, @{r[2]}), value = @{value}, name = '@{name}'")
    
So it would be much easier for you to construct complicated texts instead of
using annoying `paste`.
