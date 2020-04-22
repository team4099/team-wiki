Learning from our Mistakes
==========================

Summary
-------

This page contains the team history in terms of things we've done well in the 
past and things we should try to improve upon. The objective of this page as a 
whole is to ensure that we don't rely on veteran members' memories to make sure
we know what types of mistakes we may be prone to.


2015: Recycle Rush
------------------

`Recycle Rush <https://en.wikipedia.org/wiki/Recycle_Rush>`_, while widely considered the worst FRC game in history, was `not a 
bad year for our team <https://www.thebluealliance.com/team/4099/2015>`_. This 
was the highest ranking coming out of qualification matches that our team had 
ever placed in, and the robot generally did what it was supposed to. With that
said, there was definitely a lot of room for improvement.

Things We Did Well
******************

- Ranked relatively highly competitively

- Robust robot (no major component failures)

  - Things were overbuilt (the claw used to stack the totes was steel angle)

  - We had a spare claw

  - Winch driven by a steel cable

- Overall simple robot

  - Single winch actuation (no other actuations outside of drive)

  - Almost entirely COTS parts

    - KOP chassis

    - AM Toughbox gearboxes for everything (winch, slide drive omni)

Things We Did Not Do Well
*************************

- Extremely slow at stacking to any reasonable level

  - Robot was not designed to be able to quickly stack from human player 
    station or from landfill

  - Elevator did not have any closed loop control

    - If I remember correctly, we actually got PID gains working and had an
      encoder on that robot, but not with enough testing time to do anything
      with it

  - No driver practice

    - As usual, robot was barely finished by bag day, and there was no 
      practice bot for drivers to test stuff with

  - Claw was slow at intaking (required precise positioning)

    - No roller claw or anything to make intaking easier

- Poor strategic analysis

  - Good teams figured out at kickoff that this game was going to be won and
    lost in elims by the recycling cans -- we didn't realize this (though at 
    this point, we had never made elims in team history, so we didn't really
    design around elims)

  - Didn't really design around a planned usual game cycle

    - If we had, we would have been better at intaking from the human player
      station

- Driving was very iffy

  - We didn't really take driver practice seriously and as a result, our drive
    team selection wasn't ideal either. We did what we usually did until 2017,
    which was basically pick a couple of seniors a little bit before comps and
    let them drive (no tryouts, no multi year drivers, no real practice)

  - We decided to use a slide drive, which didn't really work but took a ton 
    of time to get working to the level that it did

    - We had the typical slide drive issue, where the sliding omni often 
      didn't get enough traction to make the robot actually do anything

    - Controls weren't really good enough to make it worthwhile, and neither
      was practice
  

2016: FIRST Stronghold
----------------------

`FIRST Stronghold <https://en.wikipedia.org/wiki/FIRST_Stronghold>`_, was the 
`first year our team made the elimination rounds <https://www.thebluealliance.com/team/4099/2016>`_. This was the first year of existence for the Chesapeake 
District (before this we competed in regionals) and the first year we competed 
in multiple competitions since 2012 (when we made Champs by winning the Rookie 
All Star Award). This was the most technically complex robot the team had 
built to this point, involving a lot of custom machining. As always, there 
were both good and bad things that happened this year.

Things We Did Well
******************

- Made elimination rounds

  - Weird circumstances, but we were good for exactly one high goal per match
    in a year where CHS had very few high goal shooters, so we were actually 
    worth more than the second pick teams who made two low goals per match
  
  - We were very close to making semifinals and missed out partly because in 
    the QF tiebreaker the refs missed a call on the other alliance that they 
    called on us
  
- Successfully built a very complex robot

  - This robot had a custom machined ACME lead screw (turned on the Boxford 
    lathe in rm. 199)
  
  - High goal shooter actually hit its first shot a pretty good amount of the 
    time

  - Cool software thing w/ porting Libfreenect (an open source Kinect driver) to
    ARM, requiring rewrites of a lot of it (won Innovation in Control Award)

- We built spares of critical components that had a high likelihood of failing

  - The spares were for the full system, not just the individual parts that 
    failed, so the swap could be done easily
  
- Worked with other MCPS teams (in particular, 4638 out of Northwest HS)
  
  - Went to their shop to practice on defenses and shooting high goals

  - Collaborated on building field parts (with so many defenses, each team built
    half

  - Learned from their mentors how their custom LED ring worked

  - Were able to meet till past 11pm (!!) because they kept their shop open 
    until then

- Good sponsor relations

  - A local Poolesville company (Tire and Auto?) painted and decaled our robot 
    for us
  
  - Relatively high quantity of sponsors compared to future years

- Understood the value of testing things repeatedly

  - Went to USRA to test shot

  - Tested in 4638's shop

Things We Did Not Do Well
*************************

- This robot was too complicated for our capabilities and who our team was in 
  2016

  - We didn't know enough about how to build good robots to be able to make a 
    usable high goal shooter
    
    - Needed better machining tolerances
    
    - Needed better interface between motors and shooter wheel (gearbox)

    - Needed more money to buy COTS parts instead of some jank solutions we had

      - For example: the flywheel (which had a hex hub) was held onto the mini
        CIM shaft with duct tape packed around the 8mm bore shaft to fill into 
        hex (this resulted in the wheel not spinning perfectly level and poor 
        accuracy). The better solution would have been to buy an adapter

      - **Lesson to learn:** If we need to be cheap, build a strategically 
        simpler robot but still use quality components, rather than making it 
        have tons of features but all at a poor quality.
      
    - Didn't know how to do closed loop control (couldn't put an encoder on the
      mini CIM shaft because we hadn't heard of CIMcoders, and didn't use a 
      gearbox on the flywheel)
      
      - This, obviously, resulted in poor accuracy

      - **Lesson to learn:** this one isn't an issue in modern FRC, but use 
        encoders wherever you care about consistent speeds or positions of a 
        mechanism.

    - For a multitude of reasons, the lead screw that drove the massive arm on
      the robot was not able to super accurately get to a given angle

      - We technically used closed loop control because there was a string pot 
        measuring the angle of the arm, but we used a linear regression on it 
        to compute the angle when it should have been sinusoidal (since the 
        distance from the potentiometer mount to a fixed point on a rotating arm
        varies sinusoidally with the angle of the arm)
      
      - Beyond not computing the angle perfectly (which we got around by 
        hardcoding values of the "angle" number we calculated that we wanted to 
        use), we effectively used the potentiometer as variable limit switches 
        on an open loop arm rather than a proper closed loop solution with a 
        PID loop
        
        - This kinda worked because the arm was slow, but did not reliably get
          to a position, and would always overshoot by some amount
        
      - The lead screw was mounted poorly on both ends, resulting in things 
        bending and more inaccuracies
        
        - The fixed part of the lead screw was attached to a 2x1 that was meant 
          to hold the chassis together (we used the KOP chassis in the C 
          configuration)
        
          - Actually, it may have been attached a little bit behind this, but 
            regardless of the actual mount, that mount regularly failed

            - regularly as in multiple times per competition

        - The moving part of the lead screw was attached to a threaded rod on 
          the arm

          - This threaded rod would bend within like three actuations of the arm

          - **Lesson to learn:** Don't use threaded rod in structural 
            applications or as a shaft taking radial load. It isn't designed for
            that.

    - We completely overlooked the second most critical subsystem on the robot 
      because we were focused on making the lead screw and shooter work well

      - We put off the intake until very late in the season and only had a 
        rough idea of what it would generally do

        - **Lesson to learn:** Have a full conceptual design of the robot before
          fleshing out anything. Use CAD and conceputal sketches for this. This
          will help avoid issues where all of a sudden nothing fits together as
          it should.

      - The intake actually ended up matching pretty well with what our rough
        concept was but the concept was bad

        - Basically it was a non-roller intake that was meant to receive
          balls and flip up, rolling the ball down the shooter arm into the
          shooter
        
        - If I remember correctly, this did not work (like, ever, including in
          the shop)

        - We tried to make it better by adding a "tripwire" to the bottom of
          it so if a ball hit it the tripwire would activate and automatically
          lift the intake to make the ball go down the ramp

          - The tripwire broke because it was literally twine hot glued to 
            a pair of tiny limit switches
          
      - **Lesson to learn:** any intake should probably be a rolly grabber, but 
        if its trying to intake balls and isn't a roller, it *will not work*

        - The ball will just roll off of or away from your intake otherwise

- We went with the wrong strategic analysis

  - There were so many decisions we could have made that would have made this 
    robot function better, but unfortunately we missed on almost all of them
  
  - There was actually a group at kickoff who identified the correct strategy 
    for our team, which was to build a bot that could cross all of the 
    defenses and score low goals
    
    - For reference, this was 1418's strategy and they won CHS DCMP that year

    - We didn't do this because we thought it would be too easy and would leave
      us with too much time in the season

      - We didn't consider the value of driver practice here

      - **Lesson to learn:** Running out of robot tasks to do in the build 
        season is a *good thing*. That's how you actually get good testing and 
        practice time.

  - If we were determined to build a high shooting robot, we should have built
    a tall robot that couldn't do the low bar

    - This was also a winning strategy, with many Einstein level teams building
      high bots that couldn't do the low bar

    - Significantly less complicated because we would have avoided the whole 
      lead screw
    
  - If we were determined to build a low bot that could shoot high, we should 
    have avoided building an arm that went high up to shoot

    - One of the best shooters at events we played in was 4638, who built a low
      bot that shot high, and it worked pretty well. Additionally, this was the
      strategy of lots of elite teams, including many who didn't worry about the
      climb for simplicity purposes.

- The way we implemented this robot led to lots of problems with robustness, 
  which in addition to being a problem by itself, led to other problems

  - The lead screw and associated parts regularly broke (some of this was 
    detailed above)

    - The lead screw itself failed regularly, with enough load being placed on 
      its threads that they would fail on a somewhat regular basis
    
    - In addition to the threads failing, with earlier iterations of the lead
      screw, there was not enough support for the lead screw to prevent it from
      buckling, so there was a lot of bending stress on the screw itself (which
      lead screws are not equipped to take well)

    - **Lesson to learn:** Lead screws are not meant to take radial load, only 
      axial load. If you build a linear actuator like we did here, use some
      other setup to take all the radial load (perhaps a telescoping tube). 
      Generally speaking, make sure you understand what types of load a system
      is designed to take before you design it to take any load.

  - The robot design required electronics to be tucked away in a super small 
    space, so we used 3D printed motor controller risers (basically let us put
    2 Talon SRs vertically, and 2 more back to back with those). These were 
    tucked into a super tiny space, but made maintenance nearly impossible on 
    these parts. 
      
    - Specifically, since the lead screw failed so frequently, we had spares 
      ready to swap in. Unfortunately, this meant the motor had to be swapped,
      which meant (at least early in the season before we connectorized 
      everything) the motor controller had to be disconnected from the motor. 
      This was nearly impossible to do with how the motor controllers were 
      situated. This packaging made what should have been a simple repair take
      absolutely forever.

    - **Lesson to learn:** No matter how unlikely you think it is that you will
      need access to a component, don't make it absolutely impossible to access
      it. If you're very confident you won't need to service it, and it makes
      packaging significantly better, you may be able to get away with it, but
      try to avoid it whenever possible. Even roboRIOs can fail in some 
      circumstances, so nothing is truly safe from being swapped.
    
  - The drivetrain was designed to go over all of the defenses, but due to 
    fears about robustness, we didn't really attempt going over defenses like 
    the rock wall and other jarring defenses after a while at competitions.

    - The problem was not the fears, the problem was that they were rational 
      fears
    
    - The jarring hits from dropping over some defenses genuinely had a good 
      chance of damaging the lead screw

    - **Lesson to learn:** Test the full robot under realistic conditions (in
      this case, it would be driving over the defenses) and make sure nothing
      is going to be shaken up. Better to break it in the shop than to take it
      to comp and have it unexpectedly break there.

- We used the coach as an on-field programmer to fix issues with the robot, 
  rather than to guide strategy or to help with driver practice

- As in 2015 and before, there was no true driver practice, and no true good 
  method to choose drive team members

  - Interestingly enough, the human player was actually a merit based decision
    based on how well they bowled the boulders when testing the intake

- While cool, the custom vision solution for this game did not work well in 
  competition

  - The UDOO board's processor was not supported by anything outside of the most
    mainstream software, so when we used an open source Kinect driver, it did
    not work with the UDOO. This added significant complexity.
  
  - The UDOO's power jack was really bad (a particularly bad barrel jack) so it
    would often lose power as soon as we started driving. 
  
  - The networking solution for communication between the UDOO and the roboRIO
    resulted in the whole robot hanging when it couldn't get a response back 
    from the UDOO. This issue could cause us to get stuck after auto for almost
    the whole match.

  - **Lesson to learn:** The hard part of a custom vision solution isn't the 
    computer vision part, but rather the whole system integration. That means 
    powering the coprocessor, the LEDs, and communicating between the 
    coprocessor and the roboRIO. If any of that fails, your CV code is useless.
    If we want to look at doing a custom vision solution again, make sure we 
    have gotten all of these issues resolved before the start of a build season.

  - The Kinect's mounting location was not chosen ideally, resulting in it 
    getting damaged an unfortunate amount.

    - **Lesson to learn:** Especially for system critical sensors, but really 
      for all electronics/sensors, we have a tendency to forget about including
      them in early design revisions. This often leads to non-ideal mounting, 
      which is not good if it leads to critical sensors not being reliable. 
      Make sure you know where sensors and such are going to go *before* the 
      robot design is locked in to avoid this issue.

2017: FIRST Steamworks
----------------------

`FIRST Steamworks <https://en.wikipedia.org/wiki/FIRST_Steamworks>`_ was a game 
for which we did many things right, improved on a lot from the previous year, 
and yet had some small issues that had a `really big impact on the competition 
season. <https://www.thebluealliance.com/team/4099/2017>`_. This robot was by 
far simpler than previous years' robots, the prototyping process was (initially)
well thought out, and our strategic analysis was pretty accurate. Unfortunately,
electrical issues and problems with our climber mechanism prevented us from
making elims in a year that put a very high emphasis on each robot being able 
to reliably climb.

Things We Did Well
******************

- The initial strategic analysis we went with was pretty accurate

  - We recognized that fuel would not be worth scoring for our team

  - We recognized that the climb was very highly weighted in this game and 
    therefore that climbing would be critical

- We (finally) realized how important driver practice was

  - Our driver was our programming lead, who spent hours tuning the drivetrain
    controls and driving around the robot, leading to some pretty good driving
  
  - We actually used the coach position as a strategic position, telling the
    drivers which gears to attempt to pick up and when to come back for the 
    climb

  - We practiced with the full drive team there during unbag hours

    - Human player, pilot, both drivers, and coach were there for almost all of
      this practice time
  
- Because of this driver practice, the robot was actually pretty well tested 

- During the prototyping phase, we recognized that using a roller system to 
  pick up gears off of the ground would be the best way to reliably grab gears

- We finished the robot very early for our team (about a week to spare I think?)

- We used pneumatics for the first time in team history

- Mechanically, the simplicity of the robot made it fairly robust

  - There were still some parts that broke (drawer slide for gear intake, 
    sheet metal on gear intake bending, grip material failing, etc.) but on the
    whole less mechanical failures than 2016 by far

Things We Did Not Do Well
*************************

- Electrical issues

  - In part due to the cost of Anderson connectors, but also because we for some
    reason decided to go against conventional wisdom for what connectors to use
    on the robot, we used electrical deans rather than Anderson Powerpoles.

    - While as far as I can remember, we didn't have any in-match failures due 
      to this decision, it made re-connectorizing each component way harder 
      because it had to be soldered. 
    
    - **Lesson to learn:** There are far better places to cut corners than 
      electrical connectors. If a critical connector fails, or takes too long to
      replace in a competition, you've lost a match, which you definitely paid
      more for than you would have for good quality connectors.

  - There were many occasions where we would get hit and brown out or lose 
    connection to the robot mid-match. Eventually we traced this down to a few 
    issues:

    - We had not purchased new batteries for a long time. We were relying on 
      old KOP batteries for a while, because team budget was low for a few 
      years. This meant we had less margin for high current draw/loose wires to
      cause brownouts.

      - **Lesson to learn:** Whenever possible, replace competition batteries 
        every two years. If not possible, use the battery beak to check internal
        resistance of the batteries, and remove the bad ones from rotation.

    - Battery cables were not tight on a lot of our batteries. This meant that 
      when hit, or sometimes even just when on the field, we would not be able
      to move because the voltage going to motors, the radio, and the roboRIO 
      was not high enough

      - Oddly enough, this wasn't a big enough issue to present itself during 
        practices or in the pit. We only saw this issue on the field, which was
        what made it so difficult to troubleshoot.

      - **Lesson to learn:** Check the electrical connections in a competition
        style setting. This means ramming the robot into walls and shaking it
        a bunch to make sure nothing loses connection and your voltage doesn't 
        drop

    - Some soldered electrical connections were not perfect, but covered with
      black heat shrink tubing, which obscured the problem.


- The electrical board was made of perforated metal (not sure if it was steel 
  or aluminum, which was cut to size and used as a bellypan. This material was 
  very sharp on the edges, and also not very stiff with everything mounted on 
  it, leading to:

  - People would semi regularly get cuts on their hands when lifting the robot 
    or when doing electrical maintenance

  - The entire electrical board would sag down

- While there was a lot of driver practice, it didn't apply super well to the 
  actual competition field for a couple of reasons:

  - When we practiced, we didn't practice with bumpers on. Unfortunately, our
    gear intake was significantly impacted by this: it was far more effective 
    when it stuck outside the frame than when it was tucked into the bumpers.

  - We practiced in the church gym, which was actually an accurate scale model
    of the field, but we didn't practice with the obstructions of two airships
    in the way. This led to drivers not relying on the camera for seeing where
    to pick up gears from, so this was a new thing they had to do at competition

    - To make this worse, we had more latency on the camera during competition 
      than at practice because of the bandwidth limit on the competition field

    - For various reasons, the driver camera (run through the same UDOO system
      as 2016) was still not very reliable, regularly dropping out mid-match,
      which was part of the reason drivers didn't want to rely on the camera
  
  - We didn't practice climbing (don't remember why)

- The climber didn't really work very well

  - Though we did test it a few times, we didn't test it in a competition 
    setting (this means driving the robot into the rope and trying to line up 
    the rope like you would in competition)

  - The climber spool was very short, requiring a lot of precise alignment

  - When the rope spooled up a bit, it would get pinched on the end of the spool
    diagonally, leading the robot to get stuck and not go up

  - The climber motor was a BAG motor which was not geared down enough to give 
    it enough margin to be able to power through issues like the above

- We were hesitant to make changes to the robot, even when it was clear some 
  things didn't work as well as they should have

  - This is good to a point, but you also have to know when to give up on a 
    failing design and move on to a different one

  - In particular, we should have changed the gear intake to a simple passive
    design when we realized that passive gear intake bots were running faster
    and more cycles than we were
  
  - We should also have revisited the climber design when it didn't work very 
    well at our first competition


- **Big lessons to learn:**

  - Make sure you practice in a competition setting. This means running your 
    cycles at the correct distance away from your drivers, making sure you use
    the robot as it will be in competition (bumpers, controls, etc), and ideally
    use carpet to practice on so game pieces and the robot behave as they would
    during competition.

  - Design the robot with the ideal cycle in mind. This means however you can,
    reduce the amount of precision the drivers need, especially when they're far
    away from the robot. Sometimes, you have to trade off between intake 
    precision required and outtake precision required (wide intake means you can
    intake easily, but the game piece isn't in as defined of a position in your
    robot). In this case, consider where you need to make the task the easiest. 
    For 2017, since intaking was far away and outtaking was right next to the 
    driver stations, it may have made sense to have a wide intake. For the 
    climber, this wasn't an issue, as it didn't really matter where on the spool
    the robot connected to the rope. The climber spool, then, could have been
    wider with essentially no negative consequences.


