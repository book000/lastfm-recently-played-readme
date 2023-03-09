# Last.fm Recently Played README

Show your recent Last.fm scrobbles on your GitHub profile README.

## What has changed in this Fork?

It is different from [JeffreyCA/lastfm-recently-played-readme](https://github.com/JeffreyCA/lastfm-recently-played-readme) in the following ways:

- **Better artwork retrieval**: Fixed an problem where artwork was not displayed for some songs.
- **Docker support**: It also works with Docker.
- **Self hosting**: [Vercel free plan has a 10-second runtime limit](https://vercel.com/docs/concepts/limits/overview#general-limits), which meant that SVGs were sometimes not displayed if it took a long time to retrieve artwork, etc. Self-hosting solves this.

This fork is hosted by following:

- `https://lrpr.amatama.net`: Self-hosting on my server. This is recommended in terms of vercel runtime.
- `https://lastfm-recently-played-book000.vercel.app`: Hosting by Vercel.

## Getting Started

Just add the following into your README and set the query parameter `user` to your Last.fm username.

```md
![My scrobbles](https://lrpr.amatama.net/api?user=book000)
```

![My scrobbles](https://lrpr.amatama.net/api?user=book000)

### Link to Last.fm profile

```md
[![My Last.fm](https://lrpr.amatama.net/api?user=book000)](https://www.last.fm/user/book000)
```

[![My Last.fm](https://lrpr.amatama.net/api?user=book000)](https://www.last.fm/user/book000)

### Custom track count

To a custom number of tracks, pass the query parameter `count` and set it to the number of tracks to display.

> Default: `5`  
> Min: `1`  
> Max: `10`

Example:

```md
![My scrobbles](https://lrpr.amatama.net/api?user=book000&count=1)
```

![My scrobbles](https://lrpr.amatama.net/api?user=book000&count=1)

### Custom card width

To set a custom card width, pass the query parameter `width` and set it to the desired width in px.

> Default: `400`  
> Min: `300`  
> Max: `1000`

Example:

```md
![My scrobbles](https://lrpr.amatama.net/api?user=book000&width=600)
```

![My scrobbles](https://lrpr.amatama.net/api?user=book000&width=600)

### Show loved tracks

Set the `loved` parameter to `true` to show a heart indicator next to your loved tracks.

> Default: `false`

Example:

```md
![My scrobbles](https://lrpr.amatama.net/api?user=book000&loved=true)
```

![My scrobbles](https://lrpr.amatama.net/api?user=book000&loved=true)

**Further customization:**

You can set the `loved_style` parameter to `1`, `2`, `3`, or `4` to customize the indicator placement.

> Default: `1`

|                                                        Style 1                                                         |                                                        Style 2                                                         |                                                        Style 3                                                         |                                                        Style 4                                                         |
| :--------------------------------------------------------------------------------------------------------------------: | :--------------------------------------------------------------------------------------------------------------------: | :--------------------------------------------------------------------------------------------------------------------: | :--------------------------------------------------------------------------------------------------------------------: |
| ![](https://lrpr.amatama.net/api?user=book000&width=300&count=2&loved=true&loved_style=1) | ![](https://lrpr.amatama.net/api?user=book000&width=300&count=2&loved=true&loved_style=2) | ![](https://lrpr.amatama.net/api?user=book000&width=300&count=2&loved=true&loved_style=3) | ![](https://lrpr.amatama.net/api?user=book000&width=300&count=2&loved=true&loved_style=4) |

## Deploying own Vercel project

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/import/git?s=https%3A%2F%2Fgithub.com%2FJeffreyCA%2Flastfm-recently-played-readme&env=API_KEY,VERCEL_URL)

Deploy your own Vercel project using the link above. Next, you'll need to set the `API_KEY` environment variable to your Last.fm API key. You'll also need to set the `VERCEL_URL` system environment variable in the Vercel project settings.

## Running locally

1. Clone Git repo
    ```sh
    $ git clone https://github.com/JeffreyCA/lastfm-recently-played-readme.git
    ```
2. Install Node dependencies
    ```sh
    $ npm install
    ```
3. Create `.env` file containing the following:
    ```sh
    API_KEY=<Last.fm API key>
    ```
4. Run development server
    ```sh
    $ npm run dev
    ```

The app will be running at [http://localhost:3000](http://localhost:3000).

## License

[MIT](LICENSE)
