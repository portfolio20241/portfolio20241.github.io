---
layout: post
modalID: modalForgetYouTubeNot
permalink: /:categories/:slug/
main_title:  Forget YouTube Not
start_date:   2018-06-01
end_date:     2018-06-02
thumb_image_url: assets/post_assets/forget-youtube-not/images/compressed/playlists-schema-cropped.png
images:
  - {
    url: "assets/post_assets/forget-youtube-not/images/compressed/playlists-schema.png",
    caption: "The schema of the database. SQL injections are prevented by the use of prepared statements, eliminating the need to keep the schema secret.",
    id: "playlist-schema"
  }
  - {
    url: "assets/post_assets/forget-youtube-not/images/compressed/typical-results.png",
    caption: "Typical results obtained by querying the database directly. I might look into providing a proper front-end for the database at some point in the future.",
    id: "typical-results"
  }
  - {
    url: "assets/post_assets/forget-youtube-not/images/compressed/deleted-before.png",
    caption: "Some of the videos were deleted before starting the project. Normally, I would still see the tile of the video after it gets deleted, but the 'deleted' bit would flip to 1.",
    id: "deleted-before"
  }
category: projects
project_title: "A YouTube polling server for detecting deleted videos"
thumb_text: A daily poll of given YouTube playlists, detecting which videos were deleted
tech:
  - pythonanywhere
  - Youtube API
  - Python
  - MySQL
size: extra-small

---

<div class="post-content-markdown">

YouTube is a wonderful source of both entertaining and useful videos, as well as a diverse source of music. Compared with Spotify, YouTube lets one find many more obscure tracks composed by less known artists, as well as less known songs or covers of renowned singers (I estimate that less than 80% of the music I like could be found on Spotify). Due to this variety available, I have created playlists with more than 3000 songs, so I could access them anytime and, most importantly, have a record of both current songs and older songs that I liked in the past. However, YouTube videos tend to be deleted every now and then. I don't mind losing access to a song, but forgetting that it exists in the first place is very annoying. That's why I made this.
{: .text-left}

I have a created a server that essentially retrieves and keeps the `(url, title)` pairs of videos in playlists of mine. The server is hosted on [pythonanywhere](https://www.pythonanywhere.com/){:target="_blank"} and uses `Python` as a back-end, `Firebase` to gain access to YouTube API and `MySQL` for storing the information. Initially I planned to use `crontab` for launching the script every day, but [pythonanywhere](https://www.pythonanywhere.com/){:target="_blank"} does not support it, providing a custom task system instead.
{: .text-left}

To use the system, the user must setup a [pythonanywhere](https://www.pythonanywhere.com/){:target="_blank"} account, create a database, create the table in it, get their own YouTube API key, and then specify the IDs of the playlists to be polled in a file on the server. Currently, only public playlists can be accessed, as no `OAuth` is set up. Lastly, there are currently no plans to have a front-end for the database, as for my purposes, accessing the results by SQL queries is enough.
{: .text-left}

The aim of the project was to provide me with a log of all videos in my playlists, since I don't have a better way of tracking all of my music. Furthermore, I wanted to investigate [pythonanywhere](https://www.pythonanywhere.com/){:target="_blank"}, which I knew about for 2+ years now, but never had the chance to use. Moreover, this was a nice refresher of my SQL knowledge. Ultimately, the project achieved all the goals I have set for it, while also taking me less than 6h to code up from scratch, with minimum background knowledge.
{: .text-left}

Code Repository: [GitLab](https://gitlab.com/LinasKo/forget-youtube-not){:target="_blank"}
{: .text-center}

</div>
