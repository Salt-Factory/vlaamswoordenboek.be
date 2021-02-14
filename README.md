# vlaamswoordenboek.be

Oude code van vlaamswoordenboek. Meeste code dateert uit 2007, geschreven in een zeer oude Ruby on Rails. Ter info. Omdat het waarschijnlijk vol gaten zit check ik voorzichtig enkele functionele stukken in ter info voor een nieuwe build from scratch.

## Run the old version with docker/podman

Should work with docker as well (replace podman with docker)

`podman run -it -p 3000:3000 -v ./:/app:Z silvioq/ruby-1.8.7  "bash"`

In the docker container

~~~
cd app/
gem instal bundler -v 1.17.3
bundle install

bundle exec rake db:schema:load
bundle exec script/runner setup.rb
bundle exec script/server
~~~

Now visit localhost:3000 and enjoy :)

Note: currently the container is stateless, every time you stop and start it again all data will
be lost (even the dependencies that were just installed)
