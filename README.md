# T20-World-Cup-2022 Stats.
import pandas as pd

import plotly.express as px

import plotly.graph_objects as go

import plotly.io as pio

pio.templates.default = "plotly_white"

data = pd.read_csv("E:\\T20-World Cup 2022\\t20-world-cup-22.csv")

print(data.head())

![t20 world cup 2022 dataset](https://github.com/Anish-Lakra/T20-World-Cup-2022/assets/86977593/e1d778da-751c-4cda-b3e9-8e1e45af4d64)

# Now let’s look at the number of matches won by each team in the world cup:
figure = px.bar(data, x=data["winner"],title="Number of Matches Won by teams in t20 World Cup 2022")

figure.show()

![No of matches Won by a team](https://github.com/Anish-Lakra/T20-World-Cup-2022/assets/86977593/8229f9eb-4705-4e54-99aa-f2224ff4d753)

# Now let’s have a look at the number of matches won by batting first or second in the t20 world cup 2022:

won_by = data["won by"].value_counts()

label = won_by.index

counts = won_by.values

colors = ['gold','lightgreen']

fig = go.Figure(data=[go.Pie(labels=label, values=counts)])

fig.update_layout(title_text='Number of Matches Won By Runs Or Wickets')

fig.update_traces(hoverinfo='label+percent', textinfo='value', textfont_size=30,marker=dict(colors=colors, line=dict(color='black', width=3)))

fig.show()

![No of matches won by runs or wickets](https://github.com/Anish-Lakra/T20-World-Cup-2022/assets/86977593/9bf73e85-b93c-41c3-9921-6785c18364fe)

# Now let’s have a look at the top scorers in the t20 world cup 2022:

figure = px.bar(data, x=data["top scorer"],y = data["highest score"],color = data["highest score"],title="Top Scorers in t20 World Cup 2022")

figure.show()

![Top Scorer in t20 world cup 2022](https://github.com/Anish-Lakra/T20-World-Cup-2022/assets/86977593/0f4b408c-295d-4e3a-8dd2-a023f47bfb73)

# Now let’s have a look at the number of player of the match awards in the t20 world cup 2022:

figure = px.bar(data, x = data["player of the match"], title="Player of the Match Awards in t20 World Cup 2022")

figure.show()

![Man of the match in multiple games](https://github.com/Anish-Lakra/T20-World-Cup-2022/assets/86977593/4d98a7d7-2a32-42e2-acd2-463e7982d6a2)

# Now let’s have a look at the bowlers with the best bowling figures at the end of the matches:

figure = px.bar(data, x=data["best bowler"],title="Best Bowlers in t20 World Cup 2022")

figure.show()

![Best Bowler of the  tournament](https://github.com/Anish-Lakra/T20-World-Cup-2022/assets/86977593/282fc30f-7f89-4819-bb7a-4ad74b3eff71)







