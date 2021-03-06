#summary World of Warcraft addon for defining teams of multibox characters

Downloads: http://code.google.com/p/wow5box/downloads/list

== Introduction ==

MultiboxRoster is a WoW addon that lets you define teams of multibox characters. The mechanism for this is pretty
primitive at the moment. You have to edit a special LUA file and add a line like this for each team:

{{{
"teamname" = { "Toon1", "Toon2", ... "ToonN" }
}}}

One you do that MultiboxRoster will automatically recognize team changes as you add characters to a party or
raid, and it will fire a special event `MultiboxRoster_TeamChanged` that other addons can use to do interesting
stuff. Team composition and order are independent of party/raid membership and order, so you will get the same
virtual team in the battlegrounds if your toons are scattered among multiple groups or if your normal main is not
the party leader.

All of this only gets interesting if some other addon consumes the `MultiboxRoster_TeamChanged` event. At present
ActionBarTargeting is the only consumer, but lots of other cool stuff is possible.

== Setup ==

    # Copy the addon to your WoW addons folder as usual
    # Copy the file `Teams_sample.lua` to `Teams.lua`
    # Follow the instructions in the file to define your own teams (just edit a couple of lines)
    
That's it!

You should save a copy of the `Teams.lua` file somewhere outside your addons directory. If you install a new version
of the addon you will need to copy the file back to your addons directory or else go through the setup process again.
(I know this sucks -- I'm working on something better.)

If any one your toons have non-ASCII characters in their name (e.g., "Myt��n") be sure that you save Teams.lua as
Unicode with the encoding UTF-8. (Other encodings might work too, I'm not sure what WoW supports. ) Otherwise WoW won't 
be able to see the extended characters correctly and your team won't be recognized.

[https://www.paypal.com/cgi-bin/webscr?cmd=_donations&business=FJVUV4S9GXX9U&lc=US&item_name=wow5box&currency_code=USD&bn=PP%2dDonationsBF%3abtn_donateCC_LG%2egif%3aNonHosted https://www.paypal.com/en_US/i/btn/btn_donateCC_LG.gif]