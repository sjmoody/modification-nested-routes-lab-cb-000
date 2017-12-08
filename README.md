Testing
rspec spec/controllers/artists_controller_spec.rb
rspec spec/controllers/songs_controller_spec.rb
rspec spec/routing/artists_routing_spec.rb
rspec spec/helpers/artists_helper_spec.rb
rspec spec/models/song_spec.rb
rspec spec/features/artists_spec.rb
rspec spec/features/songs_spec.rb


Gameplan:
1. create new song records through an artist
  [x]a. update nested resources to include only new children
  [x]b. update songs_controller#new to handle the artist_id parameter
  c. in artists/show template, add a link to nested new song page for that artist(assuming same tests as readme)
  d. add hidden field for artist_id in the songs/_form.html.erb_ partial
  e. update strong params to support :artist_id in songs_controller
2. Editing song as a nested resource
  * Allow edit action in nested route
  * Update our song show view to give nested link to edit song for the artist (if in spec)
3. Create helper to display drop-down list of artists if someone edits song directly via /songs/id/edit; only display the artists name if they are editing through nested routing.  Helper method name is artist_select
4. Validate new songs created use valid artists otherwise redirect to /artists
5. validate that songs edited via nested routing have a valid artist; otherwise redirect to /artists
6. valudate the songs edited are in the artist's songs collection; otherwise redirect to /artists/id/songs


# Modifying Nested Resources Lab

## Objectives

1. Implement nested resources for creation and modification

## Overview

In this lab, we're going to be implementing nested resources for
creating and editing songs through an artist.

## Instructions

1. Using nested resources, set up routes and controller actions to
   create new `song` records through an `artist`. **Hint:** Don't forget
to update the strong parameters.
2. Set up routes and controller actions to support editing a `song` as a
   nested resource of an `artist`.
3. Create a helper to display a drop-down list of artists if someone
   edits a song directly via `/songs/id/edit` and to only display the
artist's name if they are editing through nested routing. Name the
helper method `artist_select`. **Hint:** You'll need to set a variable
in the controller action to pass to the helper method as an argument
along with a `song` instance.
4. Validate that new songs created for an artist via nested routing are
   created for valid artists, and redirect to `/artists` if not.
5. Validate that songs being edited via nested routing have a valid artist. Redirect to `/artists` if not.
6. Validate that songs being edited via nested routing are in the
   artist's `songs` collection. Redirect to `/artists/id/songs` if not.
7. Make sure all tests pass!

<p data-visibility='hidden'>View <a href='https://learn.co/lessons/diy-nested-resources-lab' title='Modifying Nested Resources Lab'>Modifying Nested Resources Lab</a> on Learn.co and start learning to code for free.</p>
