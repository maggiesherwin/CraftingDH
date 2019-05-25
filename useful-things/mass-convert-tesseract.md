    library(magick) 
    library(magrittr)
    library(pdftools)
    library(tesseract)
    dest <- "~/(image folder)"
    myfiles <- list.files(path = dest, pattern = "jpg", full.names = TRUE)

    # improve the images
    # ocr 'em
    # write the output to text file

    lapply(myfiles, function(i){
        text <- image_read(i) %>%
        image_resize("3000x") %>%
        image_convert(type = 'Grayscale') %>%
        image_trim(fuzz = 40) %>%
        image_write(format = 'png', density = '300x300') %>%
        tesseract::ocr()

    outfile <- paste(i,"something to mark them.txt",sep="")
    cat(text, file=outfile, sep="\n")

    })
