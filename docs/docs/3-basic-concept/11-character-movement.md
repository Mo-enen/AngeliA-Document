# Character Movement

You can open the **Movement Editor** from the top-right corner of the game window to adjust how the player character moves, including parameters like movement speed and jump height. Character movement properties are stored in the project directory under `Universe/Meta/Character Movement`.

> ℹ️ Some values use a *1000-scale* (multiplied by 1000) for greater precision. For example:  
> - `1000` represents 1 unit per frame  
> - `3000` represents 3 units per frame  
> - `100` represents 1 unit per 10 frames



### Size

Adjusts the collision bounds of the character. The unit is in *global*.
<img src="../../images/MovementEditor/EN-1.gif" width="61.8%"/>


### Walking

Hold the up arrow key while moving to walk. If walking is disabled, this input is ignored.

- **Enable Walking**: When checked, the character can walk.
- **Walk Speed**: Distance moved per frame while walking (in global units).
- **Walk Acceleration**: Acceleration from low to high speed while walking (1000-scale).
- **Walk Braking Acceleration**: Acceleration applied when moving in the opposite direction while walking (1000-scale).
- **Walk Deceleration**: Acceleration from high to low speed while walking (1000-scale).
<img src="../../images/MovementEditor/EN-2.gif" width="61.8%"/>


### Running

This is the default movement mode. In mid-air, horizontal speed depends on either walking or running speed.

- **Enable Running**: When checked, the character can run.
- **Run Speed**: Distance moved per frame while running (in global units).
- **Run Acceleration**: Acceleration from low to high speed while running (1000-scale).
- **Run Braking Acceleration**: Acceleration applied when moving in the opposite direction while running (1000-scale).
- **Run Deceleration**: Acceleration from high to low speed while running (1000-scale).
<img src="../../images/MovementEditor/EN-3.gif" width="61.8%"/>


### Jumping

- **Max Jump Count**: Maximum number of consecutive jumps after touching the ground.
- **Jump Speed**: Initial vertical velocity when jumping (in global units).
- **Jump Release Multiplier**: While ascending, releasing the jump key multiplies the current velocity by this value (1000-scale).
- **Jump Hold Gravity Multiplier**: While holding the jump key and ascending, gravity is multiplied by this value (1000-scale). Default gravity applies during descent.
- **Momentum Jump Boost**: If jumping while moving horizontally, a portion of the horizontal speed (scaled by this multiplier, 1000-scale) is added to the jump speed.
- **First Jump Roll**: The first jump after touching the ground plays a rolling animation.
- **Subsequent Jump Roll**: Non-initial jumps after touching the ground also trigger a rolling animation.
- **Jump Cancels Dash**: Pressing the jump key during a dash will cancel the dash.
- **Jump Cancels Sprint**: Pressing the jump key during a sprint will cancel the sprint.
- **Enable Crouch Jump**: When enabled, the character can crouch and jump. This conflicts with sprinting, and is only allowed when sprinting is disabled.
- **Drop Through One-Way Platforms**: While standing on upward one-way platforms, press down + jump to drop through. This takes priority over sprinting and only works when on such platforms.
<img src="../../images/MovementEditor/EN-4.gif" width="61.8%"/>


### Crouching

- **Enable Crouch**: Allows the player to press down to crouch.
- **Crouch Height Scale**: Multiplier applied to collider height while crouching (1000-scale).
- **Crouch Move Speed**: Movement speed while crouching (in global units).
- **Crouch Acceleration**: Acceleration from low to high speed while crouching (1000-scale).
- **Crouch Deceleration**: Acceleration from high to low speed while crouching (1000-scale).
<img src="../../images/MovementEditor/EN-5.gif" width="61.8%"/>


### Sprinting

- **Enable Sprint**: Allows sprinting by pressing down and jump together.
- **Sprint Height Scale**: Collider height during sprint (1000-scale).
- **Sprint Roll Animation**: Character performs a roll animation during sprint (visual only).
- **Sprint Extinguishes Fire**: Allows the character to extinguish flames on contact while sprinting.
- **Sprint Speed**: Speed during sprint (in global units).
- **Sprint Duration**: Duration of a sprint in frames.
- **Sprint Cooldown**: Frames to wait before sprinting again.
- **Sprint Acceleration**: Acceleration from low to high speed while sprinting (1000-scale).
- **Sprint Cancel Velocity Multiplier**: When a sprint is canceled (e.g., by jumping), the character’s speed is multiplied by this value (1000-scale).
<img src="../../images/MovementEditor/EN-6.gif" width="61.8%"/>


### Dashing

- **Enable Dash**: Allows dashing by double-tapping the left or right arrow key.
- **Dash Height Scale**: Collider height during dash (1000-scale).
- **Allow Air Dash**: Enables dashing in mid-air.
- **Allow Water Dash**: Enables dashing while in water.
- **Allow Climb Dash**: Enables dashing while climbing.
- **Allow Crouch Dash**: Enables dashing while crouched.
- **Dash Extinguishes Fire**: Dashing extinguishes flames on contact.
- **Dash Speed**: Speed during dash (in global units).
- **Dash End Speed**: Speed after a dash ends (in global units).
- **Dash Duration**: Duration of a dash in frames.
- **Dash Stun Duration**: Time after dash during which the character is immobile (in frames).
- **Dash Cooldown**: Frames to wait before another dash.
- **Dash Acceleration**: Acceleration from low to high speed (1000-scale).
- **Dash Deceleration**: Acceleration from high to low speed (1000-scale).
<img src="../../images/MovementEditor/EN-7.gif" width="61.8%"/>


### Slipping

- **Enable Slipping**: When enabled, characters will slip when walking on colliders labeled with the `Slip` tag.
- **Slip Acceleration**: Horizontal acceleration from low to high speed while slipping (1000-scale).
- **Slip Deceleration**: Horizontal acceleration from high to low speed while slipping (1000-scale).
<img src="../../images/MovementEditor/EN-8.gif" width="61.8%"/>


### Ground Slam

- **Enable Ground Slam**: While airborne, press the down key to start a ground slam. Release to stop.
- **Slam Extinguishes Fire**: Contacting the ground during a slam extinguishes flames.
- **Slam Speed**: Downward velocity during slam (in global units).
<img src="../../images/MovementEditor/EN-9.gif" width="61.8%"/>


### Swimming

- **Enable Swimming**: When enabled, entering water automatically switches the character to swim mode. Otherwise, water slows movement and resets jump count without changing the movement type.
- **Water Speed Multiplier**: Multiplier applied to movement speed in water (1000-scale).
- **Swim Collider Width Scale**: Multiplier for collider width while swimming (1000-scale).
- **Swim Collider Height Scale**: Multiplier for collider height while swimming (1000-scale).
- **Swim Speed**: Movement speed while swimming (in global units).
- **Swim Jump Speed**: Initial vertical velocity when jumping in water (in global units).
- **Swim Acceleration**: Acceleration while swimming (1000-scale).
- **Swim Deceleration**: Deceleration while swimming (1000-scale).
<img src="../../images/MovementEditor/EN-10.gif" width="61.8%"/>


### Climbing

- **Enable Climbing**: Allows climbing on `trigger` colliders with `Climb` or `ClimbStable` tags. `ClimbStable` aligns the character's X position to the collider.
- **Allow Jump While Climbing**: Enables jumping while in climb state.
- **Climb Speed X**: Horizontal climb speed (in global units). Not supported on `ClimbStable`.
- **Climb Speed Y**: Vertical climb speed (in global units).
<img src="../../images/MovementEditor/EN-11.gif" width="61.8%"/>


### Flying

- **Enable Flying**: After all jumps are used, pressing the jump key again initiates flight.
- **Flight Height Scale**: Collider height during flight (1000-scale).
- **Glide When Idle**: The character continues flying forward even without directional input.
- **Flight Cooldown**: Cooldown time after flight ends, in frames.
- **Flight Lift Speed**: Initial upward speed when flight starts (in global units), reset upon ground contact.
- **Flight Upward Gravity Multiplier**: Gravity multiplier while flying upward (1000-scale).
- **Flight Downward Gravity Multiplier**: Gravity multiplier while flying downward (1000-scale).
- **Flight Fall Speed**: Constant downward speed during flight (in global units).
- **Flight Move Speed**: Horizontal speed during flight (in global units).
- **Flight Acceleration**: Acceleration from low to high speed (1000-scale).
- **Flight Deceleration**: Deceleration from high to low speed (1000-scale).
<img src="../../images/MovementEditor/EN-12.gif" width="61.8%"/>


### Wall Slide

- **Enable Wall Slide**: Allows the character to slide down vertical walls.
- **Slide on Any Surface**: Enables sliding on any surface without the `NoSlide` tag. Otherwise, only surfaces with the `Slide` tag are valid.
- **Reset Jump on Slide**: Wall sliding counts as ground contact for resetting jumps.
- **Wall Kick Speed**: Horizontal speed when jumping off a wall (in global units).
- **Slide Fall Speed**: Downward speed while wall sliding (in global units).
<img src="../../images/MovementEditor/EN-13.gif" width="61.8%"/>


### Ledge Grab

- **Enable Top Grab**: Allows grabbing onto `GrabTop` colliders from below.
- **Enable Side Grab**: Allows grabbing onto `GrabSide` colliders from the side.
- **Top Grab Height Scale**: Collider height while grabbing top (1000-scale).
- **Side Grab Height Scale**: Collider height while grabbing side (1000-scale).
- **Reset Jump on Grab**: Grabbing a ledge resets the jump count.
- **Allow Drop Down from Grab**: While on `GrabTop`, press down + jump to drop and initiate a grab.
- **Allow Climb Up from Grab**: While grabbing, press up to climb over the ledge.
- **Climb Over Duration**: Time to climb over a ledge (in frames).
- **Grab Move Speed X**: Horizontal speed while grabbing top (in global units).
- **Grab Move Speed Y**: Vertical speed while grabbing side (in global units).
- **Side Grab Kick Speed**: Horizontal kick-off speed when jumping from side grab (in global units).
<img src="../../images/MovementEditor/EN-14.gif" width="61.8%"/>


### Falling

- **Enable Falling**: Enables the falling state, during which the character is immobilized but takes no damage.
- **Slip Causes Fall**: Falling is triggered after slipping for a certain duration.
- **Fall Duration**: Duration of the fall state (in frames).
- **Run to Fall Time**: Frames of continuous running on slippery surfaces before falling. Walking does not trigger a fall; sprinting causes instant fall.
- **Fall Deceleration**: Speed reduction rate while falling (1000-scale).
<img src="../../images/MovementEditor/EN-15.gif" width="61.8%"/>


### Pushing

- **Enable Pushing**: Allows the character to push certain obstacles while moving. The pushed object must be a `Rigidbody` with `AllowBeingPush` set to `True`.
- **Push Speed**: Movement speed while pushing an object (in global units).
<img src="../../images/MovementEditor/EN-16.gif" width="61.8%"/>
