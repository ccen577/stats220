# Let's creat a meme !
```{r}
library(magick)

## square one
meat <- image_read("https://images.squarespace-cdn.com/content/v1/53b839afe4b07ea978436183/1608506169128-S6KYNEV61LEP5MS1UIH4/traditional-food-around-the-world-Travlinmad.jpg") %>% 
  image_scale(500)

## square two
eat_m <- image_blank(width = 500,
                     height = 500,
                     color = "#000000") %>%
  image_annotate(text = "Happy meat",
                 color = "#FFFFFF",
                 size = 80,
                 font = "Impact",
                 gravity = "center")

## square three
vege <- image_read("https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRm8mqBXhq-lG8smgEig9xulwEI9fgtMI7UqA&usqp=CAU") %>% 
  image_scale(500)

## square four
eat_v <- image_blank(width = 500,
                     height = 500,
                     color = "#000000") %>%
  image_annotate(text = "healthy vege",
                 color = "#FFFFFF",
                 size = 80,
                 font = "Impact",
                 gravity = "center")

## making each row

## first
top_row <- image_append(c(meat, eat_m))

## second
bottom_row <- image_append(c(eat_v, vege))

c(top_row, bottom_row) %>%
  image_append(stack = TRUE) %>%
  image_scale(800)

## my_meme
meme <- image_read("http://localhost:15289/session/preview.jpeg?viewer_pane=1&capabilities=1&host=http%3A%2F%2F127.0.0.1%3A47555")

image_write(meme, "my_meme.png")
```

**The reason I created this meme:**
* Simply just because I was hungry
  - then I was thinking what to eat by the time...
  - *meat or vege?*
* I want to show something really stands for my feelings
* The easiest way that comes up to my mind was - *Creating a meme!*
 
 
