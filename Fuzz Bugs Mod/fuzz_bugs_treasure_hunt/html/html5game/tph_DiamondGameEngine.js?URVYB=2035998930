// main
var canvas                    = document.getElementById('canvas');
var gm4html5_div              = document.getElementById('gm4html5_div_id');
var canvas_parent_div         = document.getElementById('canvas_parent');
var play_but                  = document.getElementById('play_button');
var game_width                = canvas.width;
var game_height               = canvas.height;
var is_mobile                 = isMobile();
var is_app_focused            = document.hasFocus();
var show_rotate_device_screen = false;
var show_loading_screen       = true;

// preloader
var loadingProgress           = 0;
var loadingHidden             = false;

var preloader_bar_x           = game_width*0.5;
var preloader_bar_y           = game_height*0.8;
var preloader_bar_width       = game_width * 0.5;
var preloader_bar_height      = 20;

var bar1 = document.getElementById('GM4HTML5_loadingbar');
var bar2 = document.getElementById('GM4HTML5_loadingbar2');

var c = 1, t = 1;

 
dg_initialize();

function barUpdate()
{
  if (loadingProgress < 0.88)
  {
    loadingProgress += 0.01;
    setTimeout(barUpdate, 30);
  }
}

//////////////////// Functionality ////////////////////

function dg_initialize()
{
    // PRELOADER SETUP

    if (!show_loading_screen) dg_hide_loading(); else
    resizeLoadingImg();


    barUpdate();

    // SCROLL GAME TO THE TOP OF THE BROWSER

    window.addEventListener('scroll', function () 
    {
    // Do not scroll when keyboard is visible 
    if (document.activeElement === document.body && window.scrollY > 3) {
        document.body.scrollTop = 0;
        }
    }, true);    

    // GAME BROWSER FOCUS CONTROL

    window.onfocus = function()
    {
         is_app_focused = true;
    }

    window.onblur = function()
    {
         is_app_focused = false;
    }

    play_but.onclick = dg_hide_loading;


}


function isMobile() 
{
  try{ 
    document.createEvent("TouchEvent"); return true; }
    catch(e){ return false; }
}


function getDocWidth() 
{
  if (self.innerHeight) {
      return self.innerWidth;
      }

  if (document.documentElement && document.documentElement.clientHeight) {
      return document.documentElement.clientWidth;
  }

  if (document.body) {
      return document.body.clientWidth;
  }
}

function getDocHeight() 
{
  if (self.innerHeight) {
      return self.innerHeight;
    }

  if (document.documentElement && document.documentElement.clientHeight) {
    return document.documentElement.clientHeight;
  }

  if (document.body) {
    return document.body.clientHeight; 
  }
}

function dg_show_pb()
{
  if (play_but)
  {
        play_but.style.display       ="block";
        play_but.style.pointerEvents = 'auto';
  }

    if (bar1 != null)
    {
      bar1.style.display        ="none";
      bar1.style.visibility     ="hidden";
      bar1.style.pointerEvents  = 'none';
      bar1.parentNode.removeChild(bar1);
      bar1 = null;
    }

    if (bar2 != null)
    {
      bar2.style.display        ="none";
      bar2.style.visibility     ="hidden";
      bar2.style.pointerEvents  = 'none';
      bar2.parentNode.removeChild(bar2);
      bar2 = null;
    }

  loadingProgress = 1;

   /*if (bar1)
    {
      bar1.style.display        ="none";
      bar1.style.visibility     ="hidden";
      bar1.style.pointerEvents  = 'none';
      bar1.parentNode.removeChild(bar1);
    }

    if (bar2)
    {
      bar2.style.display        ="none";
      bar2.style.visibility     ="hidden";
      bar2.style.pointerEvents  = 'none';
      bar2.parentNode.removeChild(bar2);
    }*/
}

function resizeLoadingImg()
{
  var imgLoad       = document.getElementById("GM4HTML5_loadingscreen");
  var imgBar        = document.getElementById("GM4HTML5_loadingbar");
  var wbr           = getDocWidth();
  var hbr           = getDocHeight();
  var lp            = loadingProgress;
  play_but          = document.getElementById('play_button');
  var pbs           = 150;

  if (play_but)
  {
    play_but.style.left = wbr*0.5 - 70 + "px";
    if (hbr < wbr)
    {
      //pbs = 150;
      play_but.style.top  = hbr*0.81 - 70 + "px"; 
    } else
    {
      //pbs = 80;
      play_but.style.top  = hbr*0.65 - 70 + "px"; 
    }

  }


  // loading screen
  if (show_loading_screen)
  if (imgLoad)
  if (game_width > game_height)
  { 
    imgLoad.style.width = wbr +"px";
    imgLoad.style.height = wbr/game_width * game_height +"px";
    imgLoad.style.left = 0 + "px";
    imgLoad.style.top  = 0 + "px";
  } else
  {
    imgLoad.style.height = hbr +"px";
    imgLoad.style.width = hbr/game_height * game_width + "px";
    imgLoad.style.left  = (wbr-hbr/game_height * game_width)/2 +"px";
    imgLoad.style.top     = 150*hbr/game_height + "px";
  }

 var barh = 0.03;
 var barw = 0.5;
 var barx = 0.5;
 var bary = 0.75;

  if (hbr > wbr) barh = 0.020;
  if (hbr > wbr) barw = 0.6;
  if (hbr > wbr) bary = 0.52;

  // bars
  if (lp < 1)
  {
  if (show_loading_screen)
  if (bar1 && bar2)
      {
        bar1.style.height        = hbr * barh +"px";
        bar1.style.width         = wbr * barw + "px";

        bar1.style.left          = (barx - barw/2) * wbr +"px";
        bar1.style.top           = (bary - barh/2) * hbr+ "px";

        bar2.style.height        = hbr * barh +"px";
        bar2.style.width         = wbr * barw * lp + "px";

        bar2.style.left          = (barx - barw/2) * wbr +"px";
        bar2.style.top           = (bary - barh/2) * hbr+ "px";

      }
  } else
      {
        /*if (bar1)
        {
          bar1.style.display        ="none";
          bar1.style.visibility     ="hidden";
          bar1.style.pointerEvents  = 'none';
          bar1.parentNode.removeChild(bar1);
        }

        if (bar2)
        {
          bar2.style.display        ="none";
          bar2.style.visibility     ="hidden";
          bar2.style.pointerEvents  = 'none';
          bar2.parentNode.removeChild(bar2);
        }*/
    }


  // rotate screen
  if (show_rotate_device_screen) 
  if (is_mobile == true)
  {
    var imgRotate       = document.getElementById("rotatescreen");
    if (imgRotate)
    if (game_width > game_height)
    {
      if (hbr > wbr) 
      {
        imgRotate.style.left          = 0 +"px";
        imgRotate.style.top           = 0 + "px";
        imgRotate.style.height        = hbr +"px";
        imgRotate.style.width         = wbr + "px";
        imgRotate.style.display       ="block";
        imgRotate.style.pointerEvents = 'auto';
      } else
      {
        imgRotate.style.display       ="none";
        imgRotate.style.pointerEvents = 'none';
      }
    } else
    {
      if (hbr < wbr) 
      {
        imgRotate.style.left          = 0 +"px";
        imgRotate.style.top           = 0 + "px";
        imgRotate.style.height        = hbr +"px";
        imgRotate.style.width         = wbr + "px";
        imgRotate.style.display       ="block";
        imgRotate.style.pointerEvents = 'auto';
      } else
      {
      imgRotate.style.display       ="none";
      imgRotate.style.pointerEvents = 'none';
      }
    }
  }

  // run again in 0.5 sec
  setTimeout(resizeLoadingImg, 500);
}

// Based on FMS loading
function dg_loading_function(_graphics, _width, _height, _total, _current, _loadingscreen) 
{
  //loadingProgress = 1/_total * _current;
  c = _current;
  t = _total;
}

function dg_hide_loading()
{
    if (bar1 != null)
    {
      bar1.style.display        ="none";
      bar1.style.visibility     ="hidden";
      bar1.style.pointerEvents  = 'none';
      bar1.parentNode.removeChild(bar1);
      bar1 = null;
    }

    if (bar2 != null)
    {
      bar2.style.display        ="none";
      bar2.style.visibility     ="hidden";
      bar2.style.pointerEvents  = 'none';
      bar2.parentNode.removeChild(bar2);
      bar2 = null;
    }

    var imgBar        = document.getElementById("GM4HTML5_loadingscreen");
    if (imgBar)
    {
      imgBar.style.display        ="none";
      imgBar.style.visibility     ="hidden";
      imgBar.style.pointerEvents  = 'none';
      imgBar.parentNode.removeChild(imgBar);
    }

    imgBar        = document.getElementById("GM4HTML5_loadingbar");
    if (imgBar)
    {
      imgBar.style.display        ="none";
      imgBar.style.visibility     ="hidden";
      imgBar.style.pointerEvents  = 'none';
      imgBar.parentNode.removeChild(imgBar);
    }

    if (play_but)
    {
      play_but.style.display        ="none";
      play_but.style.visibility     ="hidden";
      play_but.style.pointerEvents  = 'none';
      play_but.parentNode.removeChild(play_but);
    }


    if (canvas_parent_div)
      canvas_parent_div.style.display = "block";

    loadingHidden = true;
}

function dg_eval(code)
{
  eval(code);
}

function dg_set_document_body_color(newColor)
{
  document.body.style.backgroundColor = newColor;
}

function dg_set_document_title(newTitle)
{
  document.title = newTitle;
}

function dg_set_button_params(buttonID, _x, _y, _width, _height )
{
  var b = document.getElementById(buttonID);
  if (b)
  {
    var wbr           = getDocWidth();
    var hbr           = getDocHeight();
    var scale_scr     = hbr/game_height;

    b.style.left = (wbr-scale_scr * game_width)/2 + _x - _width * 0.5 + "px";
    b.style.top = (hbr-scale_scr * game_height)/2 + _y - _height * 0.5 + "px";
    b.style.width = _width * scale_scr + "px";
    b.style.height = _height * scale_scr + "px";
    b.style.pointerEvents = "auto";
  }
}

function dg_get_loading_hidden()
{
  return loadingHidden;
}

function dg_disable_button( buttonID )
{
  var b = document.getElementById(buttonID);
  if (b) b.style.pointerEvents = 'none';
}
