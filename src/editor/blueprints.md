# Blueprints

Blueprints are a system for saving and loading prefabricated assets. They are similar to schematics, but with a different structure optimized for searching and viewing. 

## Creating a blueprint

A **Blueprint** can be created by having content in your clipboard and pressing Ctrl+P. This brings up the **Create Blueprint** menu. In here you can do a few things, you can name your blueprint, add authors, tags and rotate your blueprint to generate a thumbnail to easily recognize it later.

Authors, tags and names are all ways by which you can easily look up blueprints later. For example by searching the tag ‘tree’ or ‘structure’ you can find all blueprints that include that tag. There are a couple dozen default tags that Axiom ships with in order to cover a wide array of possible blueprints but if those don’t quite cover your needs you can always create your own tag by clicking the ‘+’, entering the name and clicking the ‘Create Tag’ button inside the ‘Add Tag’ menu.

When you save a blueprint a file system dialog opens up native to your operating system. This confirms the name you want to give to the blueprint and lets to save it as a .bp file on your local computer. This means that you can easily create blueprints in one world or server and then use them in another world without having to deal with messy import or export schemas. The files themselves are stored in your .minecraft folder under `.minecraft/config/axiom/blueprints`

## Sharing blueprints

The blueprint files themselves can be sent to others who can then also use them in Axiom if they place the files in the designated file location. The blueprint folder supports nested directories as well, meaning that you can for example, put all your trees in one folder under the blueprints folder.

## Loading blueprints

Once you have Blueprints, you can view them in the **Blueprint Browser**. You'll be able to see thumbnails for all of your blueprints, as well as perform searches or filter by tags. Clicking a blueprint will 'open' it and place the blocks into your [clipboard](blocks_and_clipboard.md#clipboard).
