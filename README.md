# Floating-Countdown

• conteinerBlockClass = Conteiner father Class<br/>
• countdownConteinerHeight = Countdown conteiner Height<br/>
• menuHeight = Site menu height<br/>
• spaceStartEnd = Spacing for top and bottom, use 0 if you want the countdown to stay aligned on the top and bottom of the Conteiner father.<br/>
• conteinerCountdownClass = Countdown conteiner Class<br/>
• effectSpeed = Speed of the animate<br/>


**Call:**
`floatingCountdown(conteinerBlockClass,countdownConteinerHeight,menuHeight,spaceStartEnd,conteinerCountdownClass,effectSpeed)`
<br/><br/><br/>
**Ex:**<br/>
`floatingCountdown(".sub-block",80,90,20,'.cronometro-conteiner',700);`
<br/>

**Function:**
```
    //START - Floating Countdown
    function floatingCountdown(conteinerBlockClass,countdownConteinerHeight,menuSiteHeight,spaceStartEnd,conteinerCountdownClass,effectSpeed){
        $(window).scroll(function() {
            //blockStart > Conteiner father shows up on screen
            var blockStart = ($(conteinerBlockClass).offset().top - menuSiteHeight);
            //blockEnd > (Conteiner father leave screen) - (Space from countdown Height + Menu Site Height + layout space)
            var blockEnd = ($(conteinerBlockClass).height())+($(conteinerBlockClass).offset().top)-(countdownConteinerHeight+menuSiteHeight+(spaceStartEnd*2));
            
            //if Conteiner father on Screen/countdown zone
            if(($(window).scrollTop() > blockStart) && ($(window).scrollTop() <  blockEnd)){
                    //Animate Style Top from countdown conteiner
                    $(conteinerCountdownClass).stop().animate({ top: ($(window).scrollTop()-blockStart)+spaceStartEnd }, effectSpeed);
            }
        });
    }
    //END - Floating Countdown 
``` 

                                                                                           
**Clean Function:**
```
    //START - Floating Countdown
    function floatingCountdown(conteinerBlockClass,countdownConteinerHeight,menuSiteHeight,spaceStartEnd,conteinerCountdownClass,effectSpeed){
        $(window).scroll(function() {
            var blockStart = ($(conteinerBlockClass).offset().top - menuSiteHeight);
            var blockEnd = ($(conteinerBlockClass).height())+($(conteinerBlockClass).offset().top)-(countdownConteinerHeight+menuSiteHeight+(spaceStartEnd*2));
            
            if(($(window).scrollTop() > blockStart) && ($(window).scrollTop() <  blockEnd)){
                    $(conteinerCountdownClass).stop().animate({ top: ($(window).scrollTop()-blockStart)+spaceStartEnd }, effectSpeed);
            }
        });
    }
    //END - Floating Countdown 
```        
