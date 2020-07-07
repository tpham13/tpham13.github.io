---
layout: post
title:      "What I Learned from My First CLI Project "
date:       2020-06-27 23:58:09 -0400
permalink:  slow_and_steady_wins_the_race
---

The second month into my coding bootcamp at Flatiron School, we were tasked with the first CLI project. With this project, we were to write a CLI application that provide access to data that we scraped using scraping or an API from a public website.  Unlike the labs that I've been working on before, there isn't a solution waiting for me on Github if I was stuck. Although I slightly understood each lesson leading up to this project, I had no idea how to put everything together. So, my solution was to started doodling the flow of the project and soon I was able to visualize it. In many ways, this was very beneficial because once I completed the chart that represent the flow of the project, I was able to start writing some skeleton codes (naming my classes and methods) for the four classes that I would have: scraper, coffee, coffee_blend, and cli. Writing the skeleton codes out helped me outline what I should be looking for in my scraper and once the scraper class is done, I could start connecting it to other classes. Every day I wrote a few lines of code, then tested them to see if they worked and when they did work, I wrote a few more.

The website that I scraped was Philz Coffee and the  CLI application that I built was intended for the user to explore all the coffee products that Philz Coffee supplies. I scraped for the three blends (darker, medium, and lighter) that Philz Coffee supplies, then the coffees offered in each blends, and finally the description or information for each coffee. The goal here was to list out the blends then ask the user to choose the blend that they're interested to learn about. 

One of the struggles I had was that unless the users enter the blend or coffee that they want to learn about in the exact same way they were listed in the array, it will put out an error. For example, when the user was prompted to type and enter the blend that they want to learn about, the user might enter "darker blend" instead of "Darker Blend" as listed in the array. So, I used every resource at my disposal including Google, friends, colleagues, my cohort lead, and finally attending every open office hours that were available to help me solve this issue. Then a friend gave me an idea to write a method that would capitalized the first letter of every word the user enter and this would fix the issue (well, not quite): 

```
def titleize(word)

        title = word.split(" ").map { |word| nocaps.include?(word) ? 
                word : word.capitalize }.join(" ")
        title
				
end
```

The titleize method fixed the issue that I had until the user choose "Ambrosia Coffee of God" coffee under the "Lighter Blends".  The word 'of' in this coffee would be capitalized as well and this will put out the built in error message instead of the coffee description. So, the method was modified: 

```
 def titleize(word)
 
        nocaps = ["the", "of"]
				
        title = word.split(" ").map { |word| nocaps.include?(word) ? 
                word : word.capitalize }.join(" ")
        title
				
    end
```

Tada!  Now, any lowercase words that are included in the variable 'nocaps' will be kept as lowercase no matter how the user entered their choice. This project took me 10 days to complete but with a lot of helps and encouragement, I had learned a lot about asking questions, wording my questions differently for the best search results, and gaining a deeper understanding of Object Oriented Programming. 




