# NCAA-Womens-Volleyball-Serving-Project
Does serving aggression, measured by service aces, service errors, and ace to error ratio, have a meaningful relationship with team winning percentage in NCAA women’s volleyball?
Sports analytics has changed how teams evaluate performance and make decisions
because of how effective it is. Experience and what the coach notices during a match are not the
primary drivers anymore. Teams now have access to data that can uncover patterns and statistics
that are not obvious during live competition. Data is also available at a huge scale digitally, and
easily like never before too. In volleyball one of the most mentally challenging and interesting
personal experiences is serving. Serving is unique in the sport because it is one of the few actions
in a match that is completely controlled by the player and team. As well as this, all eyes in the
room are on you and hoping for either one of two outcomes. There is no defender affecting your
initial hit and because of that, the serve creates a chance to have full control on pressure on the
opponent. At the same time though, aggressive serving can lead to service errors and lost
momentum. My personal experience, and success at the service line is what drove me to work on
my project.

The main research question of this project was whether serving aggression, measured through
ace production, service errors, and ace to error efficiency, all have a meaningful relationship with

winning in NCAA women’s volleyball. This question matters because coaches, players, analysts,
and even sports betters are trying to gain a competitive edge.If serving performance strongly
predicts success, then teams may want to dedicate more training time toward aggressive serving
strategies. Fans may not think about it much too but momentum changing aces and a intimidating
serve can change the game. The goal of this project was to use real NCAA data and clean
analytical modeling to better understand how serving performance relates to winning, and to see
if it does.

Previous research already suggested that serving plays a major role in volleyball success. In one
study by Přidal, Toporová, and Priklerová, researchers analyzed over 1,600 serves during an elite
women’s international volleyball competition and found significant relationships between serve
quality and points. They found that more effective serves increased the probability of winning
rallies and concluded that “the quality of the serve can affect the outcome and the course of the
rally” (Přidal et al., 2021, p. 1365).The authors also noted that teams often won fewer rallies on
their own serve compared to when receiving, which was surprising because most people assume
serving creates an advantage automatically (Přidal, 2021).

Another recent study looked at serving strategies during the 2023 Pan American Games in elite
women’s volleyball. Laclote Gutierrez and the other writers found that power serves produced
significantly more direct points than float serves.They found that “among the power servers,
8.2% produced direct points, whereas only 2.3% of float servers produced direct points” (Laclote
Gutierrez et al., 2025, p. 5). They explained that “power serves have a critical impact on the
game by substantially increasing the odds of scoring directly” (Laclote Gutierrez et al., 2025, p.
8). This reinforces my research question that serving aggression may carry more value than

simply serving it in bounds. Most of the existing literature focuses on elite international play
though so I wanted to see if similar patterns existed in NCAA women’s volleyball.

For this project I used NCAA women’s volleyball data collected between 2012 and 2019. The
original dataset contained over 780,000 match level observations. After cleaning, organizing, and
aggregating the data at the team level, I ended up with 380 unique team season observations. The
main variables I focused on were average service aces, average service errors, ace to error ratio,
and overall team winning percentage. Winning percentage served as my target variable because
it represents team success across a full season rather than one isolated match.

Before running any models, I spent a lot of time cleaning and preparing the data in R. Missing
values were removed, duplicate observations were checked, and variables were transformed
where needed. I also created team level averages so that comparisons could be made fairly across
different programs. Some teams had extremely high serving numbers while others were way
lower..

I performed exploratory data analysis before building the models and ran testing models to see
what worked best in RStudio. Summary statistics showed that most teams had winning
percentages between about .700 and .850, with a fewer number of teams at the very top or
bottom. Average service aces showed moderate variation across teams, while service errors
showed an even wider spread. When I visualized the data using boxplots and scatterplots I saw
that teams with stronger serving numbers often appeared to have better winning percentages,
although the relationship was not perfect. Some teams had aggressive serving profiles but still
struggled overall and I noted these. I think this was a good reminder that volleyball has many
other factors in getting points.

To answer the research question I used two analytical models. My first model was multiple
regression. I built a multiple regression model using average service aces, average service errors,
and ace to error ratio as predictors of winning percentage. The purpose of this was to determine
how strongly serving variables predict team success when they are analyzed together. Before
moving forward with it, I checked basic assumptions including linearity, independence, and
residual behavior. I used the lm() function in RStudio to build the model and then visualized
residual plots and fitted values to evaluate performance. The regression results clean and helpful
for me. The model produced an R squared value of 0.6808 which means that about 68 percent of
the variation in team winning percentage could be explained by the serving variables included in
the model. Both service aces and service errors were statistically significant predictors. I found it
interesting that the ace to error ratio itself was not statistically significant in the final model, and
that this suggests that the volume of serving aggression may matter more than the the ratio alone.
Teams that consistently put pressure on opponents through aggressive serving may benefit even
if they miss a few without going overboard.

I also created a predicted scatterplot and found a strong upward trend. The predicted winning
percentages aligned closely with actual team performance. The residual plot did show some
patterning, which suggests that the model may not capture every factor affecting team success
which i ultimately expected.

My second model used K Means clustering. Unlike regression, clustering does not predict an
outcome directly. Instead, it groups teams based on similarities in their statistical profiles. For
this model I used average service aces, average service errors, and ace to error ratio as clustering
variables. I selected three clusters because it created strong separation without making the

analysis too complicated. I used the kmeans() function in R with multiple random starts to
improve stability.

The model created three distinct team groups. Cluster one contained 178 teams with an average
winning percentage of .820. Cluster two contained 167 teams with an average winning
percentage of .786. Cluster three contained only 35 teams and had an average winning
percentage of .332. Teams in cluster three consistently had weaker serving profiles and much
lower overall success. Seeing that separation made the relationship between serving performance
and winning feel even more real because it was not just one regression equation anymore. It
showed actual team identities based on serving style.

When comparing both models, each one brought something valuable. The regression model was
stronger for prediction and helped measure how much serving variables explained team success.
The K Means model was better for identifying natural team groupings and playing styles. The K
Means model is also better for visually seeing results. Both models supported the same overall
conclusion: teams with stronger serving profiles generally won more matches. The pattern stayed
consistent across both approaches.

One major limitation is that only serving variables were included. Volleyball is a complex sport
and many other variables likely influence winning percentage. Attack efficiency, passing quality,
blocking success, defensive systems, coaching decisions, and opponent strength all matter.
Volleyball is a very sensitive sport so mental factors make a huge impact because the smallest
adjustments make a big difference. Another limitation is that NCAA programs vary significantly
across conferences and competition levels. Some teams face much stronger schedules than

others, which could affect season statistics. This is true for every sport and every division as well
though. This study also only inspects the highest level of play.

Even with those limitations, the findings from this project offer useful insights for coaches and
analysts. The results suggest that serving aggression can play a major role in team success.
Coaches may want to focus less on simply avoiding service errors and more on developing
players who can serve aggressively while still maintaining control. Serving can create pressure,
disrupt offensive systems, and shift momentum in ways that basic box scores sometimes do not
fully capture.

I did not expect the relationship to be this strong. Working with real data also reminded me that
analysis is rarely clean or perfect.This study found clear evidence that serving aggression is
related to team success in NCAA women’s volleyball. Both regression and clustering analysis
showed that teams with stronger serving profiles generally achieved higher winning percentages.
While serving alone does not explain everything, it clearly matters more than many people
probably realize without playing the sport for awhile. Future research could expand this project
by including hitting efficiency, blocking performance, opponent quality, or even match situation
data. That would create an even deeper understanding of what drives success in volleyball.

References

Laclote Gutierrez, G., Azócar Gallardo, J., Vera Assaoka, T., Cresp Barria, M., Garcia Carrillo,
E., Campos Uribe, V., Báez San Martín, E., &amp; Ojeda Aravena, A. (2025). Technical tactical
analysis of serving strategies in elite women’s volleyball: Insights from the Santiago 2023 Pan
American Games. Applied Sciences, 15, 5658.

Přidal, V., Toporová, K., &amp; Priklerová, S. (2021). Effect of serve quality on the rally outcome
and course in women’s top volleyball. Journal of Physical Education and Sport, 21(3), 1361 to
1366.

NCAA Women’s Volleyball Box Score Dataset. 2012 to 2019.
