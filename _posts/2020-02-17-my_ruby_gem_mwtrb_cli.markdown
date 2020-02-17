---
layout: post
title:      "My Ruby Gem MWTRB_CLI"
date:       2020-02-17 05:52:05 +0000
permalink:  my_ruby_gem_mwtrb_cli
---


For My First Quarter Final Project I decided to create a CLI application that queries Merriam Websters Thesaurus when supplied words, and provides data for the end user.

The first step in my process was to figure out how to get an API key to acutally query the Thesauras API. For help with that I heavily utilized Merriam Websters API Documetnation on their Thesaurus API [site](https://dictionaryapi.com/products/api-collegiate-thesaurus/) . 

This documentation helped me register for an API key, and showed me how to use that API key, to query their API for information, given different sets of inputs (Words, Expressions, ...etc).

The next step for me was to build my Ruby Gem's structure, and to ensure that all files were conneting to one another from the execution file, to all of the lib files. This was a bit of a challenge in of itself,  but I was able to eventually figure out
that it would be best to have all of the require statements for the files in the lib folder, in the enviornment.rb file. From their, all I had to do was require the enviornment.rb file from my ./exec file, and I was good to go for running my program.

Next I had to. build the MWTRB_CLI, API, and Word classes to makeup the overall meat and potatoes of the program.

I started with building the API class first as I wanted to limit the scope of this class to just API querying logic as best I could, figuring that everything else would need to be handled by the MWTRB_CLI controller class. 

For the API class I gave it a single method get_data which is the method that acutally does the querying when a new instance of the API class is instantiated.

From there I started building the word class, as I knew more or less what I wanted the word object to to look like. Simply put I wanted the word class to contain all of the properties that I would later display to the end user. Things like word definition, synonyms,  antonyms, word forms, and word usage  were all stored as attributes in the Word class,  and when
the the word class is instantiated, I designed it to where it would immediately parse through all of the JSON data that the Word class receives from the API class, and pull and store the attributes accordingly in their respective attributes.

Whew ! Try saying that three times fast.

Lastly I buit the MWTRB_CLI class as I figured this would be best saved for last. Since the backbone of the program (i.e the API, and Word classes) were already built. All that was left was design the logical execution flow of the CLI's Menus and SubMenu. In addition it was at this point that I started building Data Validation, and Error Handling into my CLI as prior to this I was using very controlled input to test with. 

Finally, I tested everything, and finished going through the other parts of the Gem (README.md, gemspec files, ..etc)

Its 11:49 PM, and I'm about to upload this post as the last submission step. I feel that after everything I've been through, I can safely say that I've given it my best shot, and I believe its a good program. 

Though the perfectionist in me is saying that it could still use more work, I'm ready to submit it at this point.

It's given me so much good experience,  I'm looking forward to what the future holds.

