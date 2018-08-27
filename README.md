# YouTubePlaylistCleaner

* Bookmarked javascript that will remove 'watched' entries from a YouTube playlist.  
  * Watched entries are at least 95% viewed/progress.  
  * Delay of 100 ms is to allow YouTube site time to process deletions.

* Last updated (2018-08-27)
* For use with YouTube playlist, such as:  https://www.youtube.com/playlist?list=XXXXXXXXXXXX&disable_polymer=true

## Create a bookmark with:

javascript: ( 
function() {     
	var watched = 95;   
	var el = document.getElementsByClassName('resume-playback-progress-bar');   
	var i = el.length - 1;   
	var interval = setInterval(
		function() {   
			if (i >= 0) {       
				if (parseInt(el[i].style.width,10) >= watched) {           
					el[i].parentElement.parentElement.parentElement.getElementsByClassName('pl-video-edit-remove')[0].click();       
				}       
				i--;   
			} else {          
				clearInterval(interval);   
			}  
		}
	, 100);   
} 
)();

## In a single line, the bookmark is:
javascript: ( function() { var watched = 95; var el = document.getElementsByClassName('resume-playback-progress-bar'); var i = el.length - 1; var interval = setInterval(function() { if (i >= 0) { if (parseInt(el[i].style.width,10) >= watched) { el[i].parentElement.parentElement.parentElement.getElementsByClassName('pl-video-edit-remove')[0].click(); } i--; } else { clearInterval(interval);   } } , 100);   } )();
