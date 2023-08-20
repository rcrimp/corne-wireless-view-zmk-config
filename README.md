# TODO
- [ ] Fully migrate to Dockerfile
- [ ] Mount volume docker command

## Using the Dockerfile...

Repo under: `/home/reubenc/git/zmk-docker/`

Mount volume (or copy files):
`./config/ : /workspaces/zmk/zmk-config/`

### Build

```bash
cd /workspace/zmk/app

west build -d build/left -b nice_nano_v2 -- -DSHIELD="corne_left nice_view_adapter nice_view" -DZMK_CONFIG=/workspaces/zmk/zmk-config/

west build -d build/right -b nice_nano_v2 -- -DSHIELD="corne_right nice_view_adapter nice_view" -DZMK_CONFIG=/workspaces/zmk/zmk-config/
```

### Flashing
```bash
mv /app/build/zephyr/left/zmk.uf2 /run/media/reubenc/NICENANO
```

```bash
mv /app/build/zephyr/right/zmk.uf2 /run/media/reubenc/NICENANO
```

### Custom Art
Move contents of either/bith:
- `rubiks-shield.c`
- `vim-shield.c`
to `/app/boards/shields/nice_view/widgets/art.c`

Created with: https://lvgl.io/tools/imageconverter
- Color format: `CF_INDEXED_1_BIT`
- Output format: `C array`
- input file: `shield-art.xcf`

Instructions here:
https://www.reddit.com/r/ErgoMechKeyboards/comments/15t3o6k/custom_art_on_niceview_displays/
