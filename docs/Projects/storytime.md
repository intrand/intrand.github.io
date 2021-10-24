# storytime

`storytime` was an attempt at recreating an experience as a child using discord instead of a room full of kids/people.

!!! info "Rules"
    The activity works like so...

    Someone has a sheet of lined paper and writes a single word to start a story. That person then passes the paper to the person next to them. The recipient then writes the next word in the sentence/story. The paper is again passed to the next person and the process repeats until the story is complete.

## Design

`storytime` was comprised of three parts:

1. `db`: A Mongo database that stored all of the stories metadata related to each entry within a story.
2. `api`: An API server that handled all of the requests to/from the database.
3. `discord`: A discord bot which joined servers and listened for new messages in a configured channel id for that server (also configured by id). It was the gatekeeper / main interface to the API server.
4. `web`: A web server that used template-driven page generation to take data from the API server and make a clean, readable web page.

Users would type their message into the designated discord channel and the bot would react to tell you if the message was accepted or not.

!!! info "discord bot reactions"
    :material-check: = message was accepted and recorded<br/>
    :material-close: = message was too long, contained something really nasty (html, etc), or there was some kind of error on the back-end<br/>
    :material-help: = unknown status; check your story on the site and perhaps try again, depending on whether or not it made it in</br>

## Fatal flaws

There's one obvious flaw to making a bot, website and database to record, show and store stories, respectively: you can just do this using discord natively. All it takes is agreement from the community to follow the rules of telling a story together.

| &nbsp; | storytime | discord |
| :--- | :---: | :---: |
| Easy to write stories | :material-close: | :material-check: |
| Easy to read stories | :material-check: | :material-close: |
| Persistent | :material-check: | :material-check: |
| Avoided clutter | :material-check: | :material-close: |
| Low maintenance | :material-close: | :material-check: |
| Secure | :material-close: | :material-check: |
<!-- |  | :material-close: | :material-check: | -->

It was frustrating to go between a webpage to read the story, and discord to write the story. These shouldn't have been separate. See the conclusion for more thoughts on this.

## Conclusion

Building a set of services around using discord wasn't the right design choice for this project. I think this would work far better as a web-only service that people could sign up for using their discord, google, github or whatever identity provider(s) they wanted.
