---
layout: page
title: World War II 
subtitle: How did it impact the movie industry ?
---

- [Genre analysis](#genre-analysis)
- [Natural language processing 😵](#natural-language-processing-)
- [Movie plot summaries analysis](#movie-plot-summaries-analysis)
- [Ethniciy analysis](#ethniciy-analysis)

# Genre analysis 



Imagine you’re relaxing on your sofa, ready to watch an old movie from the 1940s. Out of curiosity, you type "best movie 1942" into Google — the year of your grandfather's birth. To your surprise, the top three highest-rated films from that year, according to [IMDb](https://www.imdb.com/list/ls023869890/?year=1942%2C1942&sort=user_rating%2Cdesc ), are about **crime** and **death**.

This sparks your interest: could it be a coincidence, or was there a broader trend in movie genres at that time?



{% include_relative assets/figures/WW2/Movies/movie_genre_us_ww2_12_00_01.html %} 

To investigate, you look at the percentage of film genres with significant variation in a five-year range before and after 1942. The results reveal that genres like **war films**, **propaganda films**, and **combat films** increased in their occurence in the cinema. The data even highlights a peak, reflecting a rise in these types of films around this period.

Considering that World War II took place from 1939 to 1945, it becomes clear that the war influenced cinematic themes. The shift in genres appears to have started around 1940 and continued until around 1948.
You want to understand this trend a bit more, so you decide to focus on the "war film" genre across each of the main included continents: North America, Europe, and Asia.

{% include_relative assets/figures/WW2/Movies/War_film.html %} 

In 1943, war films represented more than 11% of films in Europe — a percentage that had doubled compared to 1941. A similar doubling occurred in the North America, while Asia experienced a significant increase as well. By 1946, the percentage of war films in all three continents had nearly returned to its original level.
Looking further back, an earlier peak is noticeable in Asia in 1938 and 1939, which is not observed in Europe or North America. Intrigued by this anomaly, you consult a history book and discover a possible explanation: the Second Sino-Japanese War, which began in 1937 and ended in 1945. The start of this conflict may have induced the initial surge in war films in Asia.



<div class="container1">
  <div class="image">
    <img src="{{ '/assets/img/casablanca.jpg' | relative_url }}" alt="Casablanca">
  </div>
  <div class="text">
    <p> You return to your sofa to start watching the movie “Casablanca”, which has an IMDb rating of 8.5 and is about the war. As you watch, you notice that the film serves as propaganda against the Nazis
    It's time for a movie break with some fun data analysis. This time, you focus on the <strong> propaganda movie genre </strong>.  </p>
  </div>
</div>
<style>
.container1 {
  display: grid;
  align-items: center; 
  grid-template-columns: 1fr 2fr;
  column-gap: 5px;
  margin-left: auto;
  margin-right: auto;
  }

  img {
    max-width: 100%;
    max-height:100%;
  }
</style>


![All continent](/assets/figures/WW2/Movies/Propaganda_by_continent.jpg){: .mx-auto.d-block :}

You observe an increase in the production of propaganda films across all three continents you studied, starting from 1942. However, Europe shows a notable peak in 1940, right at the beginning of the war.
By splitting Europe into two categories: Germany and the rest of Europe, you discover that the peak is primarily driven by German films. What a surprise !

![zoom_germany](/assets/figures/WW2/Movies/zoom_germany.jpg){: .mx-auto.d-block :}


# Natural language processing 😵

Intrigued by earlier findings, a doubt arises: could the peaks in certain movie genres during World War II be unrelated to the war itself? To explore this, you decide to analyze movie plots from that period, focusing on the genres identified earlier.

You sit again on your sofa, take a deep breath and try to remember your history lessons... You recall that the years before the war were marked by rising antisemitism in Europe, while the post-war period emphasized the condemnation of the Nazi regime and the celebration of resistance efforts.

To investigate, you conduct a **sentiment analysis** on the characters, isolating plot summaries featuring negatively perceived characters. You then divide the data into three periods: before the war (1930-1938), during the war (1939-1945), and after the war (1945-1955). The goal is to verify whether negatively perceived characters were more likely to follow some trends - for example being Jewish before the war and Nazis or Germans after. 

By analyzing the words associated with these negative characters in the three different periods, you aim to reveal these supposed trends. You decide to plot the words that exhibit the most significant differences for the periods before and during war, and for the periods during and after war.

<div class="menu">
  <button class="menu-item" onclick="showContent('content1')">Before During</button>
  <button class="menu-item" onclick="showContent('content3')">During After</button>
</div>

<div id="content-section">
  <div id="content1" class="content">
    <h2>Before During</h2>
    <img src="{{ '/assets/figures/WW2/NLP/NLP_before_during.png' | relative_url }}" alt="Image 1">
    <p>You first have a look at the comparison between the period before the war and during the war. <i>Bingo</i> ! You realize the words that show the largest differences are actually related to war : <b> enemy, soldier, criminal, assassin, battle, spade...</b> Some of them even seem to be specifically related to world war II : <b> train, pilot, Vienna, Italy, Soviet, Stalin, Paris. </b> </p>
    
  </div>

  <div id="content3" class="content" style="display:none;">
    <h2>During After</h2>
    <img src="{{ '/assets/figures/WW2/NLP/NLP_during_after.png'| relative_url }}" alt="Image 3">
    <p>You then examine the comparison between the period during the war and after the war. <i> Bingo </i> again ! You find a lot of words related to world war II, but now there is also the topic of resistance : <b> Hitler, nazi, resistance, antinazi, guerilla, Reich, France, Vichy, axis, Germans, Führer, Mussolini...</b> </p>
    
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
You did not find exactly what you expected, but you are definitely convinced the peaks in certain movie genres were not a coincidence !
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
    border-radius: 10px;
  }
  .menu-item:hover {
    background-color:rgb(255, 187, 0);
  }
  .content {
    text-align: center;
  }
</style>


# Movie plot summaries analysis

You wish to dig deeper into the plot summaries analysis. You wish to analyze the plot summaries of all movies across various genres in the movie industry, not only the 10 of them you chose before, to see whether the war had an impact on the whole movie industry. With this in mind, you proceed to compute statistics based on the plot summaries.

First, you look at the expected number of words before and after World War II. To ensure the analysis is meaningful, you filter out words that appear too infrequently, removing those with an expected frequency of less than 0.001. After some calculations, you obtain the top thirty words with the largest ratio of occurrences.

{% include_relative assets/figures/WW2/Plot/WW2_plot_ratio_1e-3.html %} 

What does that tell us ? You observe that certain words have become significantly more frequent after the war. For example, "**tank**" appears roughly 11 times more often, "**japanese**" about 10 times more, and "**terrorist**" roughly 8 times more. Some words, such as "alex" or "sandy," are too specific and we would want more general words. So, you decide to filter more aggressively, removing words with an expected frequency lower than 0.01. 

{% include_relative assets/figures/WW2/Plot/WW2_plot_ratio_1e-1.html %} 

Now, you are pleased to see more general terms. For instance, "phone" appears approximately 4 times more frequently, and "camera" about 3 times more often. These results seem reasonable, as technology is used a lot more after WWII. Among the more general terms, you also find words like "**mission**," "**u.s**.," and "**killing**" appearing about 3 times more often. While you cannot definitively attribute these shifts to WWII, you keep these findings in mind for future analysis when you focus on specific time periods.

Okay, good. Now, you decide to fit a scatter plot comparing the expected number of words represented with probability of occurence before and after WWII with a linear regression.


![WW2_plot_regression](/assets/figures/WW2/Plot/WW2_plot_regression_2.png){: .mx-auto.d-block :}

The slope of the linear regression is approximately 1.37, suggesting that the expected frequency of a word tends to increase over time. This is simply because that plot summaries have gotten longer, with an average increase of about 1.37 times, which makes sense but doesn't provide much insight for our current analysis. However, we can use this regression line to identify interesting keywords by focusing on those that deviate the most from the line. This approach helps "normalize" the analysis by accounting for the general trend of longer plot summaries over time. You plot the ten words that deviate most from the regression line.


{% include_relative assets/figures/WW2/Plot/WW2_plot_furthest_regression.html %} 

From this, you observe that the theme of "**killing**" seems to have gained more prominence after WWII, as the word "**kill**" appears more frequently.

Next, you shift your focus to movies containing specific keywords. You first think of terms like "**Nazi**," "**Hitler**," "**Axis**," "**Allied**," and "**Jew**." You examine the number of movies featuring these keywords over time.

{% include_relative assets/figures/WW2/Plot/WW2_key_words_occurence.html %} 


It’s not surprising that the word "Nazi" peaks in the middle of WWII, but you notice that its frequency goes down already in 1944. We can not see it in the plot but you find that after 1950, between 3 and 10 movies per year contain the key word "Nazi", making it a theme. Similarly, the keywords "Hitler," "Axis," and "Allied" show a similar pattern, although with smaller magnitudes. The keyword "Jew" is more intriguing. We see growth leading up to WWII, then a slight decline during the war. You look at the time afterwards and you see a resurgence after 1960. This suggests that, in response to the atrocities committed against Jewish people, the film industry may have initially been cautious but gradually returned to addressing the topic in the post-war years.

You find this pattern interesting but decide it would be more insightful to focus on specific time periods. You examine the years during the war along with the years just before and after. You recall the words "mission," "u.s.," "killing," and "kill" and add them to your keyword list. You then plot the percentages of movies containing these keywords within the defined time periods.

{% include_relative assets/figures/WW2/Plot/WW2_plot_percentage_before_during_after.html %} 

Once again, we see that the word "Nazi" was heavily used during the war, likely in propaganda films. The terms "Hitler," "Axis," and "Allied" follow the same pattern as before. The word "Jew" shows a noticeable decline during the war. Turning to the newly added keywords, "Mission" follows the same pattern as previously observed, while "U.S." and "Killing" steadily increase over time. "Kill" is particularly interesting: it appears significantly more during the war compared to before and remains steady afterward.

You think to yourself that WWII darkly influenced the content of movie plot summaries. It becomes clear that certain terms, such as "tank," "japanese," or "terrorist," became much more common post-WWII, reflecting the impact of the war on film themes. Additionally, terms related to violence, such as "killing" and "kill," grew in prominence during and after the war, suggesting a shift in the narrative focus of films. These results provide insights into how WWII shaped cinematic storytelling, with evolving themes related to technology, violence, and historical reflection.



# Ethniciy analysis 

You are in your sofa still looking for movies from 1942. You noted the distribution of the ethnicity of the main character is very different than the one from nowdays. You wonder when the shift occured? Could the actor ethnicity have be influenced by major world events like World War II? You decide to investigate, focusing on 1937 -1948 years to avoid confounding factors. From what you learned from previous research, you decide to focus on North America and Europe as these continents are the most impacted by the war.


![ethnicity_WW2](/assets/figures/WW2/Ethnicity/WW2_etchnicty_distribution.png){: .mx-auto.d-block :}

Within the 10 most represented ethnicities you observe some interesting shifts between the two time periods, for example an increase in Swede's characters in Europe or a decrease in Irish American in North America. But is this linked to World War II ? Mmmmh, not really. You decide to focus on the German and Jewish characters.

For the German character representation, you do not observe any difference in the occurence between the two time periods. Most likely, because the second time period contains the War during which German were highly represented for example in propaganda films. 

Another interesting ethnicity for your analysis is Jewish people. You observe an increase in the proportion of occurences in the second time period both in North America and in Europe. The increase was however stronger in North America, which exhibits a ratio of 0.98 whereas in Europe the ratio was 0.8. To assess this observation you want to further look at the distribution of Jewish people throughout this time period.



![ethnicity_German_jew](/assets/figures/WW2/Ethnicity/German_jew_abs_evolution.png){: .mx-auto.d-block :}

In Europe, the representation of Jewish characters seems to have been impacted by the war, with an increase starting after 1945. In contrast, the 1930s saw a rise in antisemitism in Europe, particularly with the introduction of exclusion laws for Jews in Germany. During this period (from 1930’s to 1945), their representation in films remained limited, only starting to grow after the war when antisemitism began to decrease.
In North America, however, the representation of Jewish characters began to increase in the 1930s, and this trend remained consistent through the 1960s. This is coherent, with the fact that World War II had a greater impact on the Jewish population in Europe compared to that in North America.





<div class="redirect-buttons">
  <button class="redirect-button" onclick="window.location.href='{{ '/9_11' | relative_url }}'">Go to 9/11 Analysis</button>
  <button class="redirect-button" onclick="window.location.href='{{ '/' | relative_url }}'">Go to introduction</button>
  <button class="redirect-button" onclick="window.location.href='{{ '/conclusion' | relative_url }}'">Go to conclusion</button>
</div>

<style>
.redirect-button {
    margin: 0 10px;
    padding: 10px 20px;
    background-color: #FFBB00;
    color : rgb(48, 48, 48);
    color: white;
    border: none;
    cursor: pointer;
    border-radius: 10px;
  }
  .redirect-button:hover {
    background-color:rgb(48, 48, 48);
    Color: #FFBB00;
  }
  .redirect-buttons {
    display: flex;
    justify-content: center;
    margin-top: 20px;
  }
</style>