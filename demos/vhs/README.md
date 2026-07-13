# demos/vhs/

One [VHS](https://github.com/charmbracelet/vhs) tape per plugin plus `marketplace-tour.tape`. Each scripts a real session: start `claude` → `/plugin marketplace add .` → `/plugin install <name>@patterson-design` → run the plugin's slash command.

```bash
brew install vhs
vhs patterson-deck.tape        # → gif/patterson-deck.gif
for t in *.tape; do vhs "$t"; done
```

Tapes use a Patterson-navy terminal theme, 1180×640 @ 15pt. GIFs land in `gif/` — commit them if you want them inline in the plugin READMEs (each README has a commented-out `<img>` ready to uncomment).
