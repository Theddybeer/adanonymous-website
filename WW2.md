---
layout: page
title: World War 2 
subtitle: How did it impact the movie industry ?
---

- [Genre Analysis](#genre-analysis)
- [Natural language processing](#natural-language-processing)
- [Movie plot summaries analysis](#movie-plot-summaries-analysis)
- [Ethniciy analysis](#ethniciy-analysis)
- [Conclusion](#conclusion)

# Genre Analysis 


Imagine you’re relaxing on your sofa, ready to watch an old movie from the 1940s. Out of curiosity, you type "best movie 1942" into Google — the year of your grandfather's birth. To your surprise, the top three highest-rated films from that year, according to [IMDb](https://www.imdb.com/list/ls023869890/?year=1942%2C1942&sort=user_rating%2Cdesc ), are about crime and death.

This sparks your interest: could it be a coincidence, or was there a broader trend in movie genres at that time?


{% include_relative assets/figures/WW2/Movies/movie_genre_us_ww2_12_00_01.html %} 

To investigate, you look at the percentage of film genres with significant variation in a five-year range before and after 1942. The results reveal that genres like war films, propaganda films, and combat films increased in their occurence in the cinema. The data even highlights a peak, reflecting a rise in these types of films around this period.

Considering that World War II took place from 1939 to 1945, it becomes linked that the war influenced cinematic themes. The shift in genres appears to have started around 1940 and continued until around 1948.
You want to understand this trend a bit more, so you decide to focus on the "war film" genre across each of the main included continents: North America, Europe, and Asia.

{% include_relative assets/figures/WW2/Movies/War_film.html %} 

In 1943, war films represented more than 11% of films in Europe — a percentage that had doubled compared to 1941. A similar doubling occurred in the United States, while Asia experienced a significant increase as well. By 1946, the percentage of war films in all three continents had nearly returned to its original level.
Looking further back, an earlier peak is noticeable in Asia in 1938 and 1939, which is not observed in Europe or the United States. Intrigued by this anomaly, you consult a history book and discover a possible explanation: the Second Sino-Japanese War, which began in 1937 and ended in 1945. The start of this conflict may have induced the initial surge in war films in Asia.

You return to your sofa to start watching the movie “Casablanca”, which has an IMDb rating of 8.5 and is about the war. As you watch, you notice that the film serves as propaganda against the Nazis.
It's time for a movie break with some fun data analysis. This time, you focus on the propaganda movie genre. 

![All continent](/assets/figures/WW2/Movies/Propaganda%20by%20continent.jpg){: .mx-auto.d-block :}

You observe an increase in the production of propaganda films across all three continents you studied, starting from 1942. However, Europe shows a notable peak in 1940, right at the beginning of the war.
By splitting Europe into two categories: Germany and the rest of Europe, you discover that the peak is primarily driven by German films. What a surprise !

![zoom_germany](/assets/figures/WW2/Movies/zoom_germany.jpg){: .mx-auto.d-block :}


# Natural language processing



<div class="menu">
  <button class="menu-item" onclick="showContent('content1')">Before After</button>
  <button class="menu-item" onclick="showContent('content2')">Before During</button>
  <button class="menu-item" onclick="showContent('content3')">During After</button>
</div>

<div id="content-section">
  <div id="content1" class="content">
    <h2>Item 1</h2>
    <p>This is the content for Item 1.</p>
    <img src="{{ '/assets/figures/WW2/NLP/NLP_before_after.png' | relative_url }}" alt="Image 1">
  </div>
  <div id="content2" class="content" style="display:none;">
    <h2>Item 2</h2>
    <p>This is the content for Item 2.</p>
    <img src="{{ '/assets/figures/WW2/NLP/NLP_before_during.png' | relative_url }}" alt="Image 2">
  </div>
  <div id="content3" class="content" style="display:none;">
    <h2>Item 3</h2>
    <p>This is the content for Item 3.</p>
    <img src="{{ '/assets/figures/WW2/NLP/NLP_during_after.png'| relative_url }}" alt="Image 3">
  </div>
</div>


<script>
  function showContent(contentId) {
    const contents = document.querySelectorAll('.content');
    contents.forEach(content => {
      content.style.display = 'none';
    });
    document.getElementById(contentId).style.display = 'block';
  }
</script>

<style>
  .menu {
    display: flex;
    justify-content: center;
    margin-bottom: 20px;
  }
  .menu-item {
    margin: 0 10px;
    padding: 10px 20px;
    background-color:rgb(136, 136, 136);
    color: white;
    border: none;
    cursor: pointer;
  }
  .menu-item:hover {
    background-color:rgb(255, 187, 0);
  }
  .content {
    text-align: center;
  }
</style>


# Movie plot summaries analysis

You wish to look at the plot summaries of movies. You think to yourself : "Surely having a world war has changed not only the types of movies produced but the content of the movies itself too..." You then try to compute some statistics over the plot summaries. 

You first try to look at the expected number of words before and after the second world war.
You filter out words that have an expected number of appearences less than 0.001, as they appear way too rarely. After some tedious computing, you obtain the first thirty biggest ratios :

{% include_relative assets/figures/WW2/Plot/WW2_plot_ratio_1e-3.html %} 

What does that mean ? We see that the word "tank" appeared ~11 times more afterwards, "japanese" ~10 times more and "terrorist" ~8 times more. You are a bit confused by some words that are too specific, such as "alex" or "sandy". You decide to filter more aggressively and take out words that have an expected number of appearences less than 0.01 now. Again you do some computing and you obtain this :

{% include_relative assets/figures/WW2/Plot/WW2_plot_ratio_1e-1.html %} 

You are happy to find more general words. You see that the words "phone" appears ~4 times more and camera appears ~3 times more. You approve these results as technology is more obviously more present after the begginning of WW2 than before. You notice that among the plot with more general words, the words "mission", "u.s.", and "killing" appear ~3 times more.  You can not say that WW2 is the cause of the more frequent usage of these words but we keep them in mind for later, when we will analyse the plot summaries in a more specific time period.

Okay, good. You try now to fit a scatter plot comparing the expected number of words before and after WW2 with a linear regression. It looks like this :

<span style="color:green">Cheat : added picture </span>.

![WW2_plot_regression](/assets/figures/WW2/Plot/WW2_plot_regression_2.png){: .mx-auto.d-block :}

The slope of the linear regression is ~1.37, suggesting that the expected number of a word tends to grow. This naively suggests that plot summaries got longer with time and should be ~1.37 longer in expectation, which makes sense but does not help us really here. We can however use this regression line to find interesting key words; you try to find the words that are the furthest from the regression line. This would allow for a more fair analysis for the biggest/smallest ratios, as it "normalizes" the fact that plot summaries got longer with time. You plot the ten furthest words :

{% include_relative assets/figures/WW2/Plot/WW2_plot_furthest_regression.html %} 

 You then think that the theme of killing got more popular after WW2 as you see the word "kill" is present again.

Instead of looking over statistics of all words, you try to focus on movies with certain key words. As key words, "Nazi", "Hitler", "Axis", "Allied" and "Jew" come first in your mind. You try to look at the number of movies that contain these key words. 

{% include_relative assets/figures/WW2/Plot/WW2_key_words_occurence.html %} 


It makes sense that the word nazi is used a lot between 1940-1950, but you notice that it then stays constant, oscillating between 3 and 10 movies per year after 1950. The key words "Hitler", "Axis" and "Allied" present the same pattern, altough smaller in magnitudes. The key word "Jew" is more interesting. We can see growth until the beginning of WW2, where it shrinks a bit and stays constant until 1960, where it grows again. We could understand that after the atrocities comitted towards the jewish people, the movie industry may have been more prudent.

You find it interesting but it would make more sense to focus on time periods. You do that in two ways. First, you plot the years before and after the beginning of the war. Second, the years during the war, some years beforhand and some years afterwards. You remember the words "mission", "u.s.", "killing" and "kill" and you quickly add them in the key words. You plot the percentages of movies that contain the key words with respect to these time periods :

{% include_relative assets/figures/WW2/Plot/WW2_plot_percentage_before_during_after.html %} 

We see again that the word "Nazi" was very present during the war, surely in propaganda movies. The words "Hitler", "Axis" and "Allied" have the same pattern, as we have seen beforehand already. We see again that thw word "Jew" gets less frequent. You look at the newly added key words. The word "Mission" present the same pattern as we have discussed. The words "u.s." and "killing" just grow with time. "kill" is an interesting key word. It is a lot used during the war compared to beforehand and stays the same afterwards.

We have seen that the word "kill" comes back often in our analysis, telling us that the violence of the war and death surely changed/shocked all human beings and that it reflects in the movie industry. 



# Ethniciy analysis 

Did you know where the main character of your favorite movie comes from? What  about its ethnicities? 
You are in your sofa still looking for movies from 1942. You noted the distribution of the ethnicity of the main character is very different than the one from 2010. Hence, when do you think the shift was experienced? Could the actor ethnicity be influenced by capital world event like World War II? To investigate we focus on 1937 -1948 years, to avoid confounding factors. Furthermore, for statistical relevance reasons the subsequent analysis will be based on North America and Europe.


![ethnicity_WW2](/assets/figures/WW2/Ethnicity/WW2_etchnicty_distribution.png){: .mx-auto.d-block :}

Within the 10 most represented ethnicities we observe some interesting shift between the two times range, for example increase in Swedes character in Europe or decrease in Irish American in North America. Where can we found the impact of World War 2 ? If we looked at the German character representation we do not observe any difference in the occurence between the two time range. Most likely, because the second time period contain the War during which German was highly represented for example in German propaganda film. Another interesting ethnicities for our analysis is Jewish people. We observe an increase in the proportions of occurences in the second time period both in North America and in Europe. The increase was however stronger in North America, which exhibit a ratio of 0.98 whereas in Europe the ratio was 0.8. To assess this observation we want to further look at the distribution of German character and Jewish people throughout the last century.



![ethnicity_German_jew](/assets/figures/WW2/Ethnicity/German%20jew%20evolution.png){: .mx-auto.d-block :}

What is the impact on German character ? In Europe, we observe a big rise in German character which drops in 1945. Do you see the link with WW2? The end of the war coincided with a drop in German propaganda film and therefore, a consequent reduction of German representation in movies. What about the representation of Jewish ? In Europe the representation of Jewish seems to be greatly impacted by the war as the significantly decrease starting form late 1930’s towards today. In parallel, 1930’s corresponds to a rise of antisemitism in Europe, and rise of exclusion laws for Jewish in Germany. Therefore, explaining the decrease in Jewish character proportion in movies. On the other hand, the representation of Jewish character in North America does not seem to get impacted between 1940 and 1950. Hence, we know World War 2 had a greater impact on Europe Jewish population compared to American Jewish population. Then the decrease observed in Jewish representation in Europe is most likely caused by WW2

# Conclusion



<div class="redirect-buttons">
  <button class="redirect-button" onclick="window.location.href='{{ '/9_11' | relative_url }}'">Go to 9/11 Analysis</button>
  <button class="redirect-button" onclick="window.location.href='{{ '/' | relative_url }}'">Go to menu</button>
</div>

<style>
.redirect-button {
    margin: 0 10px;
    padding: 10px 20px;
    background-color: #0044FF;
    color: white;
    border: none;
    cursor: pointer;
  }
  .redirect-button:hover {
    background-color: #ffbb00;
  }
  .redirect-buttons {
    display: flex;
    justify-content: center;
    margin-top: 20px;
  }
</style>