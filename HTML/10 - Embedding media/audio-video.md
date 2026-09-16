# Audio

The `<audio>` element is used to embed **sound/audio content**.
Basic syntax:

```html
<audio src="audio.mp3" controls></audio>
```

The `controls` attribute tells the browser to display playback controls.

Without `controls`:

```html
<audio src="audio.mp3"></audio>
```

the browser may have no visible way for the user to play the audio.

## Important `<audio>` Attributes

1. `controls` - Displays the browser's audio controls.
2. `autoplay` - Attempts to start the audio automatically.
3. `loop` - Repeats the audio continuously.
4. `muted` - Starts the audio muted.

```html
<audio src="song.mp3" controls autoplay loop muted></audio>
```

## `<source>`

Instead of putting the audio URL directly on `<audio>`, we can provide multiple formats. The browser can choose a supported source.

```html
<audio controls>
  <source src="song.mp3" type="audio/mpeg" />
  <source src="song.ogg" type="audio/ogg" />

  Your browser does not support audio.
</audio>
```

---

# Video

The `<video>` element is used to embed video content.

```html
<video src="movie.mp4" controls></video>
```

A better approach is often to use `<source>`.

```html
<video controls>
  <source src="movie.mp4" type="video/mp4" />
  <source src="movie.webm" type="video/webm" />

  Your browser does not support the video element.
</video>
```

## Important `<video>` Attributes

1. `controls` - Provides playback controls.
2. `autoplay` - Attempts to play automatically. Autoplay policies can prevent this.
3. `loop` - Repeats the video.
4. `muted` - Muted autoplay is commonly allowed where unmuted autoplay isn't.
5. `poster` - Displays an image before the video starts playing.
6. `width` and `height` - Specifies the dimensions.

```html
<video
  src="movie.mp4"
  controls
  autoplay
  loop
  muted
  poster="thumbnail.jpg"
  width="640"
  height="360"
></video>
```

---

## Audio vs Video

| Element   | Used for                 |
| --------- | ------------------------ |
| `<audio>` | Sound                    |
| `<video>` | Video + optionally sound |

Both support concepts such as:

```text
controls
autoplay
loop
muted
<source>
fallback content
```

But `<video>` also has video-specific features such as:

```text
poster
video dimensions
tracks/captions
```

---

## Why `<source>` Is Useful

Different browsers and environments may support different media formats.

```html
<audio controls>
  <source src="song.mp3" type="audio/mpeg" />
  <source src="song.ogg" type="audio/ogg" />
</audio>
```

The browser evaluates the available sources and uses a compatible one.

The same idea works with video:

```html
<video controls>
  <source src="video.mp4" type="video/mp4" />
  <source src="video.webm" type="video/webm" />
</video>
```

---

## Accessibility for Audio and Video

Simply embedding media isn't enough. Users may:

- have hearing difficulties
- have vision difficulties
- be in a situation where sound cannot be played
- depend on assistive technologies

For videos containing dialogue, captions are particularly important. HTML provides `<track>` for things such as subtitles/captions.

Example:

```html
<video controls>
  <source src="lecture.mp4" type="video/mp4" />

  <track src="captions.vtt" kind="captions" srclang="en" label="English" />
</video>
```
