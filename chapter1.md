---
title: 'Chapter 1'
description: ""
free_preview: true
---

## Tidyverse review

```yaml
type: NormalExercise
key: d7d8976935
xp: 100
```

In this new exercise, you will review your skills from chapter 1 of [Introduction to the Tidyverse](https://www.datacamp.com/courses/introduction-to-the-tidyverse) by solving an exercise from scratch.

The `gapminder` dataset is available, but you’ll need to load any other library you want to use.

`@instructions`
Using the `gapminder` dataset, create a data frame of population by country, `pop_by_country_2002`, as follows.

1. Use the data from the year 2002.
2. The populations should be converted to millions of people.
3. The columns should be called `country` and `pop_millions`; drop other columns.
4. Order the rows by descending population.

Print `pop_by_country_2002` to see your result.

The first few rows should be:

|country                  | pop_millions|
|:------------------------|------------:|
|China                    |  1280.400000|
|India                    |  1034.172547|
|United States            |   287.675526|

`@hint`


`@pre_exercise_code`
```{r}
library(gapminder)
```

`@sample_code`
```{r}

```

`@solution`
```{r}
library(dplyr)

pop_by_country_2002 <- gapminder %>%
    # Filter for rows in the year 2002
    filter(year == 2002) %>%
    # Convert population to millions
    mutate(pop_millions = pop / 1e6) %>%
    # Select country and population columns
    select(country, pop_millions) %>%
    # Arrange rows by descending population
    arrange(desc(pop_millions))

# See the result
pop_by_country_2002
```

`@sct`
```{r}
ex() %>% 
  check_object("pop_by_country_2002") %>% 
  check_equal(incorrect_msg = "Did you create a tibble of 2002 gapminder data, including countries and their populations in millions, in descending order of population?")
ex() %>% check_error()
success_msg("Well done! Please go to the next exercise for a quick survey about your experience.")
```

---

## Feedback

```yaml
type: ExplorableExercise
key: 840cf90c42
xp: 50
```

Please provide your feedback on the previous exercise in the form on the right (might take a few seconds to load).

`@possible_answers`
- When you're ready, just submit the Google form and close this page :)

`@hint`


`@pre_exercise_code`
```{r}
url <- "https://docs.google.com/forms/d/e/1FAIpQLSeOYrUl-r0Wh0Pm75fYAnCJ4uUaHIKRRBRU0EqXp0Lf92rTSQ/viewform"
class(url) <- "html_link"
url
```

`@sct`
```{r}
ex() %>%
  check_mc(1, c("Correct"))
```
