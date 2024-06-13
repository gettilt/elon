<!--[[[cog
import cog
import json
with open('config.json') as file:
  config = json.load(file)
  cog.outl(f"# {config['name'].title()}")
]]]-->
# Elon
<!--//[[[end]]]-->

## Mission

Tilt's mission is to map every theme to a basket of stocks for anyone to invest in. Mappings are AI generated and expert curated.
Expert improvements are accepted if they provide a better representation of a given theme.

## Theme Prompt
<!--[[[cog
import cog
import json
with open('config.json') as file:
  config = json.load(file)
  cog.outl(config['prompt'])
]]]-->
Elon Musk is on a hot streak. Anything Elon mentions, backs, or is invests in will benefit. Tesla, X, Solar, SpaceX, Boring, Neuralink, and their suppliers will benefit. In addition crypto, Argentina, and other interest of Elon win.
<!--[[[end]]]-->

## Theme Stocks

<!--[[[cog
import cog
import csv
import json

with open('context.json') as file:
  contexts = json.load(file)

def _get_context_str_for_ticker(ticker):
  try:
    context = contexts[ticker]
    context_str = context['chat_gpt'] or context['claude'] or ""
  except KeyError:
    context_str = ""

  return context_str

cog.outl("| Ticker  | Context | Source |")
cog.outl("| ------- | ---- | ---- |")

with open('theme.csv') as file:
  reader = csv.reader(file)
  next(reader) # skip the header
  for row in reader:
    context_str = _get_context_str_for_ticker(row[0])
    cog.outl(f"| {row[0]} | {context_str} | {row[1]} |")
]]]-->
| Ticker  | Context | Source |
| ------- | ---- | ---- |
| CAT | Caterpillar could indirectly benefit from The Boring Company's infrastructure projects, requiring heavy machinery and construction equipment. | chat_gpt |
| ENPH | A solar energy company that could benefit from the growth in solar energy solutions, a sector Musk is involved in through Tesla's solar division. | chat_gpt,claude |
| GGAL | An Argentinian bank that could benefit from Musk's interest in Argentina, especially if Tesla or SpaceX expand operations or investments there. | chat_gpt |
| LMT | Lockheed Martin could see indirect benefits from the increased interest in space exploration driven by SpaceX's achievements. | chat_gpt |
| NVDA | NVIDIA could benefit from the need for advanced computing in Musk's ventures, especially in AI for Tesla and potential applications in Neuralink. | chat_gpt,twitter |
| PLTR | A data analytics company that could indirectly benefit from Musk's ventures requiring advanced data analysis and AI, like Tesla and SpaceX. | chat_gpt |
| PYPL | As Musk's former venture, PayPal could benefit from any fintech innovations or endorsements Musk makes, given his influence. | chat_gpt,google |
| SPCE | While not directly related to Musk, Virgin Galactic could benefit from the overall interest in space exploration Musk generates. | chat_gpt,google |
| SQM | A lithium producer that benefits from the demand for electric vehicle batteries, indirectly boosted by Tesla's success. | chat_gpt |
| TSLA | Directly benefits as Musk's flagship company, leading in electric vehicles and energy solutions. | chat_gpt,claude,twitter,google |
| PLUG |  | claude |
| RUN |  | claude |
| SPWR |  | claude |
| STEM |  | claude |
<!--[[[end]]]-->

## License

<p>
This project is licensed under <a href="./LICENSE">AGPLv3</a>.
</p>


## Contributors

Thank you for your improvements! We appreciate all the contributions from the community.

<!--[[[cog
import cog
import json
with open('config.json') as file:
  config = json.load(file)
  repo = config['github_repo'].lower()
  cog.outl(f'<a href="https://github.com/gettilt/{repo}/graphs/contributors">')
  cog.outl(f'  <img src="https://contrib.rocks/image?repo=gettilt/{repo}" />')
  cog.outl('</a>')
]]]-->
<a href="https://github.com/gettilt/elon/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=gettilt/elon" />
</a>
<!--[[[end]]]-->

## Join Our Community

<a href="https://discord.gg/4vYMhRpaMY" target="_blank">
<img src="https://discord.com/api/guilds/1179775688421683220/widget.png?style=banner3" alt="">
</a>
