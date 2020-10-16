# ArmaForces - Medical

## Main changes

- dressings made more efficient
- medical actions take less time to complete
- medical system made friendlier to the players (no need to keep bandaging yourself as often as before, also munch on these apap pills with extra paracetamol to easily fight the pain without worry of losing consciousness)

## Dressings

Dressings take longer to deplete their usefulness, it can take up to 30 minutes for dressing to fall off in case of correct material type being used to dress specific wound type. What's more their efficiency in wrapping up wounds is much better when compared to default ACE settings. Table below shows dressing type efficiency when used to dress specific wound type.

### Dressings efficiency table

`++` = Excellent | `+` = Increased | None = Standard

| Wound\Dressing | Field Dressing | Elastic | Packing | QuikClot |
| :------------: | :------------: | :-----: | :-----: | :------: |
|    Abrasion    |       ++       |         |         |          |
|    Avulsion    |                |   ++    |         |          |
|   Contusion    |                |   ++    |         |          |
|     Crush      |                |   ++    |         |          |
|      Cut       |       ++       |         |         |          |
|   Laceration   |       ++       |         |         |          |
|    Velocity    |       +        |    +    |   ++    |    ++    |
|    Puncture    |       +        |    +    |   ++    |    ++    |

The table below shows additional parameters worth taking into consideration when applying specific dressing. 

- timeframe throughout which it is possible for bleeding to start again,
- chance of bleeding occurring in aforementioned timeframe (if bleeding doesn't happen under these terms, it won't happen at all),
- how many wounds of specific size you can dress using specific dressing

| Efficiency            |      | +    | ++    |
|-----------------------|:----:|:----:|:-----:|
| Bleeding timeframe    | 5-10 | 6-20 | 10-30 |
| Bleeding chance       | 0.4  | 0.3  | 0.1   |
| Large wounds          | 2    | 4    | 8     |
| Medium wounds         | 3    | 5    | 9     |
| Minor wounds          | 4    | 6    | 10    |

## Fighting pain

Conscious soldiers can use new pain suppressing medication - APAP pills. These little bad boys with high dose of paracetamol are safe to use - they pose little to no chance of overdosing. The drawback is that they can't be used on unconscious units.

| Feature                            | Apap                    | Morphine                                                    |
| ---------------------------------- | ----------------------- | ----------------------------------------------------------- |
| Max efficiency time                | 10 min                  | 30 min                                                      |
| Delay before kicking in            | 2 min                   | 0.5 min                                                     |
| Painkilling strength               | 0.6                     | 0.8                                                         |
| Use case                           | Conscious units in pain | Great pain and unconscious units in pain                    |
| Side effects                       | None                    | Lowers pulse                                                |
| Chance of inducing unconsciousness | Negligible              | Very high, 2 injections might lead to loss of consciousness |

## Tourniquets 

These little devices are tight - literally. They can be put on all four limbs to stop bleeding occurring within correspondent part:

- can be only applied to arms and legs,
- drastically faster to apply than dressings, 
- multiple use - after taking them off, they go back to the backpack of person detaching them from limbs,
- after a few minutes they induce a growing pain on the person wearing them,
- medical injections (e.g. blood, saline, morphine) are inefficient when injected through limbs with tourniquet applied

## Saving pvt. Ryan - step by step

### 1. Make sure you are safe

Don't proceed with your work, when you (or your patient) are under fire. Look for a safe position to conduct the job. If you want to carry the wounded soldier on your back, apply tourniquets first - it's fast and stops the bleeding from limbs.

### 2. Unconscious teamleader

If your higher-up is unconscious or dead, pick up the radio from his body. For the time being you must either take over the leadership, or designate somebody from your team to take the reins instead.

### 3. Dressing wounds

If the patient suffered from multiple wounds on many body parts, apply tourniquets to the limbs. Start bandaging torso and head, next you can take care of the limbs. It is critical you stop the bleeding.

### 4. Resuscitation

Check whether the poor bastard has pulse or not.

#### No pulse

Check how much blood did the patient lose. Inject him with red juice if needed.
Conduct CPR. After each turn check if the heartbeat came back. If there's more than one person taking care of the wounded unit, make sure you aren't checking for pulse when somebody else is conducting CPR - you might get a bad read. Pulse didn't come back after a few CPR turns? Transfuse more blood.

#### Pulse detected

If the heartbeat is low (<45 BPM) inject Epinephrine (aka Adrenaline).
If the patient lost too much blood - blood transfusion. Duh.
Suture his wounds. If you ain't no medic and you lack stitching kit then you have to regularly check up on his injuries - apply dressings when the wounds open up. Stay vigilant - forget about the poor soul, and he might just bleed out under your nose.
