# TournaGen

[Heroku link][heroku]

[Website link][tournagen]
[TournaGen Repo][repo]

[heroku]: https://tourna-gen.herokuapp.com/
[tournagen]: http://www.tournagen.xyz/
[repo]: https://github.com/darrengtan/TournaGenhttps://github.com/darrengtan/TournaGen

## Minimum Viable Product
The Tourney's Journey is a clone loosely based off of Challonge built on Rails
and Backbone. Users can:

- [x] Create accounts
- [x] Create sessions (log in)
- [x] Fill out a tournament form
- [x] Create brackets for a tournament
- [x] Create and join teams
- [x] Follow tournaments
- [x] View a feed of followed tournaments
- [x] View a feed of hosted tournaments
- [x] Search for tournaments by title
- [x] Search for teams by name

## Design Docs
* [View Wireframes][views]
* [DB schema][schema]

[views]: ./docs/views.md
[schema]: ./docs/schema.md

## Implementation Timeline

### Phase 1: User Authentication, Tournament Form Creation (~1-2 days)
I will implement user authentication in Rails based on the practices learned at
App Academy. By the end of this phase, users will be able to fill out a form
containing necessary information to start a tournament. I will add API routes
to serve tournament and team data as JSON, then add Backbone models and
collections that fetch data from those routes. The most important part of this
phase will be pushing the app to Heroku and ensuring that everything works
before moving on to phase 2.

[Details][phase-one]

### Phase 2: Generate Tournament Brackets (~2 days)
I will use third-party libraries to generate tournament brackets from a list of
participating teams. Possible candidates for this are the Tournament gem,
bracket_tree gem, and Bracket jQuery plugin. I will need to make sure that the
team names are properly escaped to prevent malicious injections. I will also
ensure the brackets are properly formatted before I move on to the next phase.

[Details][phase-two]

### Phase 3: Tournaments Index (~1 day)
First, I will allow users to follow a tournament through a followings joins
table on the Rails side that can be shown as JSON data. Then, I will add a
`feed` route that will generate a list of the current user's created tournaments
and followed tournaments through the proper associations on the Rails side. On
the Backbone end, I will create a `TournamentsIndex` view of the current user's
created and followed tournaments. Ultimately, this will be the page users see
after logging in. I will also give them the option to view either of the two
lists in the sidebar.

[Details][phase-three]

### Phase 4: Updating Tournaments (~2 days)
Using the gems and jQuery plugins from Phase 2, I will figure out how to create
a friendly interface for users to update the tournament standings. The current
plan is to have a pop-up screen after the tournament's author clicks a specific
matchup that allows the author to say who won the match and the score. Ideally,
they will be able to add sets to the score in case the game being played
requires multiple sets.

[Details][phase-four]

### Phase 5: Searching for Tournaments and Teams (~2 days)
I'll need to add `search` routes to the Tournaments controller. On the
Backbone side, there will be a `SearchResults` composite view has
`TournamentsIndex` and `TournamentSummary` subviews. These views will use plain
old `tournaments` collections, but they will fetch from the new `search` routes.

[Details][phase-five]

### Bonus Features (TBD)
- [ ] Group stage implementation for tournaments
- [ ] Custom tournament urls
- [x] Pagination/infinite scroll
- [ ] Tournament history
- [x] Registration for tournaments
- [ ] Share tournaments
- [ ] Multiple sessions/session management
- [x] Team logos
- [x] Typeahead search bar

[phase-one]: ./docs/phases/phase1.md
[phase-two]: ./docs/phases/phase2.md
[phase-three]: ./docs/phases/phase3.md
[phase-four]: ./docs/phases/phase4.md
[phase-five]: ./docs/phases/phase5.md
