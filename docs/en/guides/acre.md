# ACRE

# About
In short, ACRE2 is a mod for Arma3 and a plugin for TeamSpeak3 (two-in-one) responsible for all communication occurring between the players in game. What it does is implementing realistic spatial hearing communication into the game - you'll be able to say which voice originates from which player, the volume is dependent on the distance between speaker and listener, radios for short, medium, and long range communication are also part of the mod. At the start of the game all TS3 clients are moved to proper channel, where they'll be able to hear only other players in close vicinity (as longs as they aren't using radios). No pokes, messages, or any other TS3 sound cues will reach players thrown into the game - they can focus on playing instead.

# Installation

1. Download the ACRE2 mod from Steam Workshop and tick it on in game launcher.
2. After booting the game for the first time after installation, ACRE2 will automatically install proper plugin in TeamSpeak3 directory. Make sure to enable the plugin (Tools -> Options -> Addons -> ACRE2 Enabled)

# Initial configuration

1. Go to Options -> Controls -> Configure addons -> Choose from the list: ACRE2
2. Delete key binding for Default radio key
3. Delete key binding for Babel Cycle language
4. Bind CAPS LOCK key to Alt radio key 1

# Configuring short-range radio (PRC-343)

PRC-343 is mostly used by infantry, to communicate inside their designated fire teams. It has effective range of 850 meters in perfect conditions, i.e. where no terrain or building obstruction is present. City range varies around 450 meters.

Short-range radio's configuration boils down to two steps:

## Setting channel block

1. Open up the radio through ACE interaction menu (Left CTRL key + Left WINDOWS key) -> Radios -> AN/PRC-343 Chn: 1 -> Open Radio
2. Detach the handle on the left side by clicking on it
3. Use the blue, square button to change channel block
4. Attach the handle back by clicking on it again

## Setting channel

1. Open up the radio through ACE interaction menu once again.
2. Use the big black knob next to the antenna to change channels - LMB switches channel up, RMB switches channel down

# Configuring medium- and long-range radios (PRC-152/117F)

These are the radios used mainly by support and command units.

PRC-152 - medium-range (effective distance in perfect conditions - 5-7km, city range 3-5km)
PRC-117F - long-range (effective distance in perfect conditions - all the way to the horizon, city range 10-20km)

Neither of the radios has block setting. Only channels can be chosen, also do note that these channels are shared between the two radios - words spoken on channel 2 of PRC-152 will be heard on channel 2 of PRC-117f and vice versa!

In most cases medium-range radio is used alongside short-range radio. To transmit on it use the combination of Left CTRL key and CAPS LOCK.

## Setting channel

### PRC-152

1. Open up the radio through ACE interaction menu (Left CTRL key + Left WINDOWS key) -> Radios -> AN/PRC-152 Chn: 1 -> Open Radio
2. Use the PRE button on the keypad (bottom right) to change channel. "+" changes channel up, "-" changes channel down. 

### PRC-117F

1. Open up the radio through ACE interaction menu (Left CTRL key + Left WINDOWS key) -> Radios -> AN/PRC-117F Chn: 1 -> Open Radio
2. Use the PRE button on the keypad (bottom right) to change channel. "+" changes channel up, "-" changes channel down. 

# Checking the radio configuration

!> After changing radio block or channel make sure it was properly set. You can start radio transmission and say something like "Bravo team, check." and await response from teammates.

# FAQ

## > I HEAR VOICES IN MY RADIO, BUT I CAN'T TRANSMIT

That saddens us deeply. Next time try not to click every button on the radio keypad, for now just take a new radio or go through basic configuration again.

## > I SCREAM AND SHOUT BUT THERE'S NO REACTION

Either you are outside the effective range, or somebody else is already transmitting on the radio.

## > ME WANTS SECOND CHANNEL, HOW?

You can't set second channel on your radio, take one more radio.

## > MY LEADER IS DEAD, THE BERLIN HAS FALLEN, SOMEBODY CALL CROSSROADS, WHAT DO?

Snatch the radio from your leader's dead body, there's no other way to reach higher-ups.
