(function($) {

    var element = $("body");
    var video = document.getElementById("video");
    var vol = 0.1;
    var interval = 15;
    var go = new TimelineLite();
    go.add("start", 1)
    go.from(element.find('main'), 1, { y: 300 }, 0, "start");
    go.staggerFrom(element.find('main section'), 1, { autoAlpha: 0, y: 150 }, 0.3, 'start');

    var tl = new TimelineLite();
    tl.add("end", 0)
    tl.to(element.find('#intro'), 2, { autoAlpha: 0 }, 0.5, "end");
    tl.staggerTo(element.find('main section'), 1, { autoAlpha: 0, y: 150 }, -0.1, "end");
    tl.to(element.find('main'), 0.2, { y: 300 }, 1.5, "endMain");
    tl.pause();

    $('#button, #nav').click(function(e) {
        tl.play();
        video.currentTime = 0;
        video.volume = vol;
        video.play();
        console.log('play');
    });


    var delay = 2000;

    $('#video').click(function(e) {
        tl.timeScale(1);
        tl.reverse();
        window.setTimeout(function() {
            video.pause();
            console.log('pause');
        }, delay);
        var fadeout = setInterval(function() {
            if (vol >= 0.01) {
                vol -= 0.01;
                video.volume = vol;
                console.log('ca va');
            } else {
                // Stop the setInterval when 0 is reached
                window.clearInterval(fadeout);
                console.log('fader');
                vol = 1;
            }
        }, interval);

    });

    var hover = new TimelineLite();
    hover.to(element.find('#button'), 1, { backgroundColor: "rgba(200, 200, 202, 0.9)", scaleX: 0.95, }, 0, "nope");
    hover.to('.turn', 1, { rotation: 360, transformOrigin: '5px 5px' }, { rotation: 2, ease: Sine.easeInOut, repeat: -1, yoyo: true });
    hover.pause();

    $('#button').mouseover(function(e) {
        hover.timeScale(1);
        hover.play();
    });
    $('#button').mouseout(function(e) {
        hover.timeScale(2);
        hover.reverse();
    });


    ////////////////////

    var mask = new TimelineLite();
    mask.add('bidule', 0)
    mask.to(element.find('menu'), 1, { y: 1000 }, 0.1, 'bidule');
    mask.staggerTo(element.find('menu ul li'), 0.8, { autoAlpha: 1 }, 0.3, 'bidule+=0.2');
    mask.to(element.find('main'), 1, { y: 300 }, 0.2);
    mask.pause();

    $('#resp').click(function(e) {
        mask.play();
    });

    $('#close').click(function(e) {
        mask.timeScale(2);
        mask.reverse();
    });

    //        $('#nav svg').mouseover(function(e){
    //        TweenLite.to($(this), 1, {rotation:-30});
    //    });

})(jQuery)