# Hosting a Bitcoin Core Review Club Meeting

## General Tips

Some tips for hosting a great review club meeting:

### Before the Meeting

- Consider contacting the PR author to let them know that you're going to
  talk about their PR in the review club. They'll probably be happy that you're
  interested in their PR and may be prepared to answer questions and give
  you more context. They may even want to join the meeting themselves.

- The Bitcoin Core maintainers created a [`Review
  club`](https://github.com/bitcoin/bitcoin/labels/Review%20club) label for us
  on GitHub; don't hesitate to ask them in the PR or on IRC (`#bitcoin-core-dev`
  or `#bitcoin-core-pr-reviews`) to tag the PR you'll be hosting.

- Try to post notes and questions on the Friday the week before the meeting.
  That gives attendees time to review the PR and prepare for the meeting.

- Prepare a range of questions from basic to advanced. The review club is a way
  to help new developers develop. There should be something for everyone.

- In the notes and meeting, don't just talk about the mechanical code changes.
  Other important aspects to consider are: the historical context of the PR (why
  things in the code are the way they are currently, and what PRs have touched
  that part of the code base), testing methodology and motivation for the PR.

- Don't feel like you need to spoon-feed the attendees. Give them pointers for
  where to look in the codebase/GitHub/documentation, and let them do their
  own research from there.

- Thorough preparation will really pay off. Taking the time to deeply
  understand the PR will make you feel more relaxed during the meeting and
  will pay dividends even months later.

- It can be useful to write out some anticipated answers/links/references
  before the meeting so you don't have to type them in the moment.

### In the Meeting

- Come with the mindset that the attendees are people who are as smart as you,
  but don't have the context that you do in Bitcoin protocol development.

- Start the meeting with `#startmeeting` and "hi" from everyone so you know
  who's at their keyboard and paying attention.

- It's nice to remind people of some of our meeting conventions at the start:

  - You don't have to ask to ask a question (e.g. "I have a question about x but
    I don't know if it's on-topic?"). Just go ahead and ask. If it's off-topic
    we'll tell you.

  - The host is there to help moderate, not to lead. You don't need to wait
    for the host to ask a specific question — just jump in at any point.

- A quick poll at the start ("Did everyone get a chance to review the PR? How
  about a quick y/n from everyone") establishes who will probably be
  asking/answering the more interesting questions.

- Don't be distressed if people haven't had a chance to review the PR yet. This
  is a voluntary meeting and most people have a lot of other commitments.

- Very open questions to the group (e.g. "Does everyone know how tx gossip works
  in Bitcoin?") sometimes fall flat because all the attendees are waiting for
  someone else to answer. Instead try to make the questions focused on the
  PR or change set that is being reviewed (e.g. "how does commit X change the
  way bitcoind gossips transactions?"). Also, try to phrase questions
  positively ("please describe how X works") rather than negatively ("Does
  anyone not know how X works?").

- When hosting, it sometimes feels like there are minutes of silence and no-one
  is out there. Be patient and don't worry! It takes people a bit of time to
  formulate their thoughts and type them out.

- Be encouraging! For many people, asking questions or volunteering an answer
  can be intimidating, even in the pseudonymous comfort of IRC. People are
  there to learn. Try to create an environment where they feel safe to ask any
  questions and where they can attempt to answer without fear.

- Keep an eye on the clock, and try to wrap up the session with `#endmeeting` at the end of the
  hour. Even if you're happy to continue beyond the hour, some of the attendees
  might have hard stops.

- Have fun, and pat yourself on the back for making Bitcoin protocol development
  stronger and more decentralized 🚀

### After the Meeting

One of the review club maintainers will:

- Copy the meeting log to the `## Meeting Log` section of the meeting post.
  Meeting logs should be copied exactly, but an `## Erratum` section can be
  added to correct factual errors.

- Change the `status` of the meeting post to `past`.

- (optionally) push a tag of the branch at the time of the meeting to the
  [PR Review Club Bitcoin repo](https://github.com/bitcoin-core-review-club/bitcoin)
  and add a `commit` variable to the PR page to add a link to the branch. This
  is so if the PR branch changes drastically after the review club meeting,
  people reading the notes and log later can see the branch as it was at the time
  of the meeting.

## Making a New Post

To make a new post, run the following Ruby make command from root or the
`_posts` directory:

```shell
rake posts:new -- --pr NUMBER --host USERNAME --date YYYY-MM-DD
```

or with short arguments:

```shell
rake posts:new -- -p NUMBER -h USERNAME -d YYYY-MM-DD
```

For more details/help, run:

```shell
rake posts:new -- --help
```

The `pr` and `host` arguments are required. The `date` argument is optional;
if none is passed the meeting date will be set by default to next Wednesday.

The `host` argument is your GitHub username.

This command will create a new markdown file for the post, with metadata and
initial Notes and Questions headers.
