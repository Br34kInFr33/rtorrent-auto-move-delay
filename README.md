# rtorrent-auto-move-delay
Move files after short delay and continue seeding.

After going through https://github.com/rakshasa/rtorrent/issues/547 I ran into a problem getting this to continue seeding after files were moved.  I figured out how to get it to continue seeding and thought I would save a copy of it here.

Just copy text from rtorrent.txt file and past it at the bottom of your .rtorrent.rc file.  No need to add a config.d folder.

Make sure to change the delay (which is in seconds), and change the complete directory to your needs.  
method.insert.value = event.download.finished_delayed.interval, **600**  
method.insert = d.get_finished_dir, simple, "cat=**~/Download/**,$d.custom1="
