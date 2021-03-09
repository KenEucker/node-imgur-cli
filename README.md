# node-imgur-cli
CLI tool for the node-imgur package

## Installation

```bash
npm install imgur-cli -g
```

## Usage

Pass binary image files, urls, and/or [base64-encoded](http://en.wikipedia.org/wiki/Base64) image strings as arguments. Globbing is supported.

Upload a single image:

```bash
imgur-cli cat.png
```

### Upload multiple images ([globbing](<http://en.wikipedia.org/wiki/Glob_(programming)>) supported):

```bash
imgur-cli cat.png cats.gif cats23.jpg

imgur-cli ~/*.(jpg|png|gif)

imgur-cli ~/Pictures/kittens/*.jpg ~/gifs/sfw/*.gif
```

### Upload an image from another place on the web. Be sure to include http(s):

```bash
imgur-cli --url https://octodex.github.com/images/topguntocat.png
```

### Upload a Base-64 encoded image:

```bash
imgur-cli --base64 iVBORw0KGgoAAAANSUhEUgAAABAAAAAQCAYAAAAf8/9hAAAAmUlEQVQ4je2TsQ3CMBBFnxMa08WR2IQKJskIUNwMZAcYwWIQMs65JCUpEEIYW4pJy6v+6e6+/hVnnGsAzsCBMi7AsbbW/rIMsAU2xrnmkeruuzW7zgIw+JGbv6fGQpWzfy3HOsJlDQY/AlCv3jpF9oS5ZBOICKoB1YCIlCdQDR9127qyBHP5Gyw3CBXPr/qi709JHXE1S995AsqoJu8x78GsAAAAAElFTkSuQmCC
```

### Saving a client id for subsequent use:

```bash
imgur-cli --save f9ae01148b53261
```

### Display saved client id:

```bash
imgur-cli --show
```

### Remove previously saved client id:

```bash
imgur-cli --clear
```

### Use a specific client id one time only (overrides saved id):

```bash
imgur-cli --client-id f9ae01148b53261 --file ~/me.jpg

# Short-hand
imgur-cli -c f9ae01148b53261 -f ~/me.jpg
```

### Add images to an existing album by specifying an album ID:

```bash
imgur-cli --album-id F8KTV --file ~/me.jpg

# Short-hand
imgur-cli -a F8KTV ~/me.jpg
```

You must own the album. If it's an anonymous album you need to use the `deletehash` in place of the album ID.

