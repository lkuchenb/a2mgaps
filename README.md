# a2mgaps

## Requirements

- numpy
- biopython
- matplotlib

## Usage

    a2mgaps <outpath.pdf> <inpath.a2m> [<inpath.a2m> ...] [OPTIONS]

    --allcols             Include all columns in the plot (also lower case
                          characters)
    --printvals           Print the numeric values in TSV format to STDOUT
    --cpos CPOS [CPOS ...]
                          Concatenation position(s) for concatenated MSAs.

## Example with data export

Export the gap statistics

    a2mgaps <outpath.pdf> <inpath.a2m> --allcols --printvals > values.tsv

Example code in R to recreate the gap plot

    library(ggplot2)
    ggplot(read.table("values.tsv", header = T)) + geom_bar(aes(x=position, y=count, fill=gaptype), stat = "identity")
