jQuery Environment Plugin [![Endorse Me](http://api.coderwall.com/pboling/endorsecount.png)](http://coderwall.com/pboling)
=========================

Allows the setting of environment specific configuration.
The jQuery equivalent of Rails' config/environments files.

NOTE:  Do not use this plugin to store 'secret' data about your app, or you will be exposing it to your DOM,
       and thereby hackety-hackers.

Use without DOM (globally):

  Option 1.

     Example:

         // Setup in a conditionally loaded script, see example/jquery-environment-config.js.erb
         $.environment({ here: 'dragon', env_name: 'production', foo: 'bar'});

         // Usage elsewhere
         $.environment.config('here');       // dragon
         $.environment.config('env_name');   // production
         $.environment.config('foo');        // bar

Two (three!) ways to use with DOM:

  Option 1. via the data-environment attribute on any HTML element.

     Example:

         <body data-environment-configuration="{foo: 'bar'}">)

  Option 2. via the instantiation options for the plugin.

     Example:

         $('body').environment({ here: 'dragon', env_name: 'production' });

  Option 3. Option 1 + Option 2

     Example:

         // Do both of the above examples and then you get this usage:
         $('body').environment.config('foo');      // bar
         $('body').environment.config('here');     // dragon
         $('body').environment.config('env_name'); // production

Author: @pboling

Version: 1.0

Release Date: November 12, 2012

Based on:  'Highly configurable' mutable plugin boilerplate by @markdalgleish and @addyosmani,
           see http://coding.smashingmagazine.com/2011/10/11/essential-jquery-plugin-patterns/

## Versioning

This library aims to adhere to [Semantic Versioning 2.0.0][semver].
Violations of this scheme should be reported as bugs. Specifically, 
if a minor or patch version is released that breaks backward 
compatibility, a new version should be immediately released that
restores compatibility. Breaking changes to the public API will 
only be introduced with new major versions.

[semver]: http://semver.org/

## License

MIT license


## Notes

Note that with this pattern, as per Alex Sexton's, the plugin logic
hasn't been nested in a jQuery plugin. Instead, we just use
jQuery for its instantiation.


[![Bitdeli Badge](https://d2weczhvl823v0.cloudfront.net/pboling/jquery.environment/trend.png)](https://bitdeli.com/free "Bitdeli Badge")

