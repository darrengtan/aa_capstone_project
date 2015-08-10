# Phase 1: User Authentication, Basic Blogs and Posts

## Rails
### Models
* User
* Tournaments
* Teams

### Controllers
* UsersController (create, new)
* SessionsController (create, new, destroy)
* Api::TournamentsController (create, new, show, update, destroy)
* Api::TeamsController (create, new, show, update, destroy)

### Views
* users/new.html.erb
* session/new.html.erb
* tournaments/show.json.jbuilder
* teams/show.json.jbuilder

## Backbone
### Models
* Tournament (parses nested "teams" association)
* Team

### Collections
* Tournaments
* Teams

### Views
* TournamentForm
* TeamForm
* TeamShow

## Gems/Libraries
