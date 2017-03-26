Ahsan Qureshi

1\. XSS Vulnerability in playlist function

	We can execute XSS using an mp3 file with a script located in the mp3's meta information.

	To prove this:

	1. We can get a malicious mp3 file from https://securify.nl/advisory/SFY20160742/xss.mp3
	2. Upload the mp3 as a media file.
	3. Start to create a post and select the mp3 file.
	4. Click Create a playlist and create a playlist using the mp3 file and create the post.
	5. Going to any page containing the playlist will activate the script in the mp3 meta info.

	Type of vulnerability: XSS

	This was fixed in 4.2.13

	Source: https://github.com/WordPress/WordPress/commit/28f838ca3ee205b6f39cd2bf23eb4e5f52796bd7

	The playlist looks like this:

<img src='http://i.imgur.com/ToAGJnh.png' title='Playlist MP3 XSS' width='' alt='Playlist MP3 XSS' />

	Here is a screenshot of the script being executed:

<img src='http://i.imgur.com/YGcYskH.png' title='Playlist Script Executed' width='' alt='Playlist Script Executed' />



2\. XSS Vulnerability in Youtube Embed

	A script can be executed through a youtube embed

	To prove this:

	1. create a youtube embed statement: [embed src='https://youtube.com/embed/12345\x3csvg onload=alert(1)\x3e'][\embed]

	2. insert this into a post and go to the page where it was posted.

	Type of vulnerability: XSS

	This was fixed in 4.2.13

	Source: https://github.com/WordPress/WordPress/commit/419c8d97ce8df7d5004ee0b566bc5e095f0a6ca8

	Here is the XSS script being executed:

<img src='http://i.imgur.com/lLdNURg.png' title='Youtube Embed XSS' width='' alt='Youtube Embed XSS' />

3\. XSS Vulnerability in shortcode

	We can execute xss through shortcode

	To prove this:

	1. Create a shortcode statment: [caption width='1' caption='<a href="' ">]</a><a href="onClick='alert(1)'">
	2. Insert this into a post

	Type of vulnerability: XSS

	This was fixed in 4.2.5

	Source: N/A

	Here is the XSS script being executed:

<img src='http://i.imgur.com/DY9x3T4.png' title='Shortcode XSS' width='' alt='Shortcode XSS' />