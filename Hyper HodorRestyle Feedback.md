## Would love to have
- Opacity slider
- Resize height automatically depending on group size
- Only enable in combat
- Allow user to resize width
- Allow users to specify height per bar
- Highlight your personal DPS

## Bugs
- Unlock UI doesn't change text when you click it

## Really picky design stuff
- Rather than having everyone damage & dps in one text element if you split each element up individually it would allow you to align each bit of text nicely.
- Option to use a monospace font for DPS values, again just to align everything nicely

## Never ask never recieve
- Option to switch alignment of entire element from left to right
- Option to put the current boss's name in the Top Bar (So that screenshots can be taken of the entire box and include all the necessary information)
- 

## Questions
            if dmgType == 1 then -- total damage
                damage:SetText(dmg/100 .. 'M || ' .. dps .. 'K')
            else -- boss fight
                damage:SetText(dmg/10 .. 'k (' .. dps .. 'K)')
            end