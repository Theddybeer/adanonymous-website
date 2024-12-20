---
layout: home
title: World changing events
subtitle: Did you see the impact from your sofa ?
---
![alt text](/assets/img/sofa_tank.jpg)

# Introduction


Movies... who hasn't watched a movie? They have been around for so long that even our great-grandparents have been to the cinema.

Movies have lived through the last century, from the silent era at the beginning of the 20th century, through the golden age of Hollywood until the 1940s. Then, adapting to the rise of television with widescreen formats and epic productions before shifting to more gritty and realistic movies in the 1960s. We have now welcomed the digital era filled with special effects-driven blockbusters and streaming services.

When you consider that it took ten centuries during the Middle Age to discover a new continent, and now only two centuries to experience three technological revolutions and two world wars, it seems clear that the pace of history has accelerated dramatically. With such acceleration, you might expect the movie industry to have an endless source of inspiration. But to what extend do real world events actually shape and influence cinema? Could a single terrorist attack in the world’s most powerful country - and home to Hollywood - be enough to alter the course of the movie industry? Or does it take a global conflict involving 70 nations to impact such an industry?

This is the question we want to answer with you, with the power of data analysis. We used the CMU data corpus.
**The CMU dataset** contains information on over 30000 movies, including their country of production, language, and genre. For some of these movies, plot summaries are also available. Additionally, the dataset provides details about the actors, the roles they played, as well as their gender and ethnicity.
Our objective is to evaluate the impact of certain historical events on world cinema using three distinct axes: the impact on movie genres, the worlds used in plot summaries, and the ethnicity of the authors.
Furthermore, we aimed to use general methods to ensure reproducibility, enabling the analysis to be extended to other historical events.

To begin, we focused on **World War II**, a global event that reshaped world history and impacted all countries. We then shifted our attention to a more "local" but still highly significant event — the **September 11 2001 attacks**.



<div class="redirect-buttons">
  <button class="redirect-button" onclick="window.location.href='{{ '/WW2' | relative_url }}'">Go to WW2 Analysis</button>
  <button class="redirect-button" onclick="window.location.href='{{ '/9_11' | relative_url }}'">Go to 9/11 Analysis</button>
  <button class="redirect-button" onclick="window.location.href='{{ '/conclusion' | relative_url }}'">Go to Conclusion</button>
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

