# YouTube Viewer
Simple program to increase YouTube views written in Python. Works with live stream too.

**Disclaimer:** This has been developed for educational purposes only. Any action you take using this script is strictly at your own risk. I will not be liable for any losses or damages you face using this script.

**Cons:** There will be some view drop always. 


# Requirements
 * **Python 3.7.x-3.9.x**
 * High speed Internet Connection
 * Good proxy list (http, https, socks4, socks5)
 * Google Chrome installed on your OS (not Chromium)


# Features
 * YouTube default, live streaming and YouTube Music support
 * Multithreaded and Dynamic thread support
 * Auto download updated chrome driver whenever user's Google Chrome version is updated
 * Patch chrome driver on the start of every thread by undetected-chromedriver
 * Proxy support 
      * location : text file (must be on path) / proxy API (should work with most of the proxy providers)
      * type : http, https, socks4, socks5
      * format : `ip:port`, `user:pass@ip:port`, `ip:port:user:pass`
      * proxy refresh after a certain time specified by the user
      * rotating proxy support
 * chrome v80+ randomized user agent based on platform
 * canvas,audio,font,webgl fingerprint defender and IP leak prevent by webrtc control
 * geolocation, timezone, referer spoofing
 * can add extra extensions in the `extension/custom_extension/` folder
 * direct link or search *keyword* on YouTube then watch the video by matching exact video *title*
 * modify **urls.txt, search.txt and config.json** on the fly without restarting program
 * HTTP api on localhost and a database to store view count
 * config.json to save settings
 * bypass consent page and several other pop up 
 * save bandwidth by reducing video quality 
 * can set higher(100%) watch duration percentage to increase *Watch time*, change playback speed
 * #### Traffic Sources
   * YouTube Search
   * Suggested Videos
   * External (Google, Yahoo, DuckDuckGo, Bing, Twitter)
   * End Screens
   * Channel Pages
   * Direct or unknown

# How to get started
  1) First, install the script following any one of these   
      * [Windows without installing python](https://github.com/Tiago08/YouTube-Viewer#binary-release)    
      * [Windows from source code](https://github.com/Tiago08/YouTube-Viewer#installation)    
      * [Linux / Mac from source code](https://github.com/Tiago08/YouTube-Viewer#linux--mac)
   2) Then put your video links in the [urls.txt](https://github.com/Tiago08/YouTube-Viewer#urls) file
   3) To search your video on YouTube and then play it put the search keywords and video title in the [search.txt](https://github.com/Tiago08/YouTube-Viewer#search) file
   4) Get your [proxy](https://github.com/Tiago08/YouTube-Viewer#proxies) list
   5) Run the script and follow the instructions from there.


# Proxies
 *[IPRoyal](https://iproyal.com?r=18862) offers datacenter and residential proxies. The Royal Residential proxies have a large pool with addresses in over 160 countries all over the world, so they can generate a massive number of views. IPRoyal agreed to provide a huge discount for my script users, so the price will be as low as 3.60USD/GB! To get this incredible 10% discount for Royal Residential proxies, use the discount code: `youtubers10`*


* ## Free Proxy
   Try not to use free proxies. But if you have a paid subscription and you want to use authenticated IP feature, then you can use the free proxy category. Provide your text file path (where you saved the proxies) when the script asks for a proxy file name or a proxy API.
   N.B: Available for **http(s)/socks4/socks5**
   
* ## Premium Proxy
   Proxies with authentication can also be done. To do so put your proxies in this format `username:password@ipaddress:port`or `ipaddress:port:username:password` in a text file. Every single line will contain a single proxy. Provide your text file path when the script asks for a proxy file name or a proxy API.
   
   N.B: Only available for **http** type proxy.

* ## Rotating Proxy
   You can also use the rotating proxies service. You can either authenticate your IP on your proxy provider service and use `ipaddress:port` as Main Gateway. 
   N.B: Available for **http(s)/socks4/socks5**

   Or direct use username:password combo like this `username:password@ipaddress:port` or `ipaddress:port:username:password` as Main Gateway.

   N.B: Only available for **http** type proxy.
   You can use proxy API too.

# HTTP API
   Live logs fetched every 10 seconds and statistics in graphs are available on http://localhost:5000/ .Or [http://ip_of_your_pc:5000/](http://ip_of_your_pc:5000/) use this to access from another device under same network. A SQLite Database is being used  to store your generated views from this script. 
   Last 200 logs from scripts are fetched every 10 seconds to show on website and graph is updated every 5 minutes.

# Config.json
   No need to type everything everytime you run the script. A config file will be created automatically to save and use your preferences.
   You can modify it on the fly without restarting the program.
   
# Urls
  Put video links in the urls.txt. For multiple videos place urls in multple lines.
  1) To find video link in YouTube click share and copy.
  2) If you have any external link which will redirect to your youtube video you can use that too. Example : when you post a YouTube video link in **twitter** and you hit play on twitter, you will get a link like this `https://t.co/xxxxxxxxxx?amp=1`. This is helpful because YouTube will see that views are coming from External Source like twitter in this example.

# Search
  Program can search youtube with the keyword you want and find video with video title. To do this you need to know what keyword can find your video on youtube search engine. Also you need to provide **exact** video title. Put keyword and title like this format `keyword :::: video title` in **search.txt**. You can use same `video title` for multiple `keyword` too.

  *If you don't know any keyword just put your `video title :::: video title` in search.txt*

   
# Live Stream
   This script supports live streams too. Just use this script as you would for the already uploaded video. Script will automatically know if your video is live. Just bear in mind, you need a **high-end pc** for higher threads to get more viewers.
   Basically, script will check every 60 secs if youtube shows `x watching now` is present. If your live stream ends, script will check 5 times to be sure. In another word, after your live stream ends, script takes 5 minutes to close the driver.
   
   If you have never used this script before, use this first for an already uploaded video. This way, you will have a better understanding of how this script works. To do so, keep reading.

# YouTube Music
   Can generate views on YouTube Music too. In **urls.txt** put your music link like this `https://music.youtube.com/watch?v=xxxxx`. Script will automatically load YouTube Music when it sees link have `music.youtube.com`. **Search feature is not available for this.** So you need to empty the search.txt otherwise it will start searching videos in default YouTube.


* ## Installation

  First, make sure you have installed git and Python version between 3.7.x to 3.9.x
  
  Open command prompt and type
  ```
  git clone https://github.com/Tiago08/YouTube-Viewer.git --depth 10
  ```
  ```
  cd YouTube-Viewer
  ```
  ```
  python -m pip install --upgrade pip wheel
  ```
  ```
  pip install "setuptools<59"
  ```
  ```
  pip install -r requirements.txt
  ```

* ## Important
   * If you've got a large free proxies collection, you should run this command to filter Good proxies. Then use **GoodProxy.txt** for proxy in **youtube_viewer.py**
      ```
      python proxy_check.py
      ```

   * After closing program, if chromedrivers are still running. You may want to double click **killdrive.bat** to close all chrome instances.

   * *urls.txt* or *search.txt* can't be empty. Otherwise you will see errors. Use both for better results.

* ## Usage
   * Open command prompt in YouTube-Viewer folder and run
        ```
        python youtube_viewer.py
        ```
   * Rest is self explanatory.

# Linux / Mac
* ## Installation

  First, make sure you have installed git and Python version between 3.7.x to 3.9.x
  
  Open your favourite terminal and run
   ```
  git clone https://github.com/Tiago08/YouTube-Viewer.git --depth 10
  ```
  ```
  cd YouTube-Viewer
  ```
  ```
  python3 -m pip install --upgrade pip wheel
  ```
  ```
  pip3 install "setuptools<59"
  ```
  ```
  pip3 install -r requirements.txt
  ```

* ## Important
   * If you've got a large free proxies collection, you should run this command to filter Good proxies. Then use **GoodProxy.txt** for proxy in **youtube_viewer.py**
        ```
        python3 proxy_check.py
        ```

   * After closing program, if chromedrivers are still running. Open your terminal and run 
      ```bash
      ps aux | awk '/chrome/ { print $2 } ' | xargs kill -9
      ```
   * *urls.txt* or *search.txt* can't be empty. Otherwise you will see errors. Use both for better results.

* ## Usage
   * Open command prompt in YouTube-Viewer folder and run
        ```
        python3 youtube_viewer.py
        ```
   * Rest is self explanatory.
 
 # Best Practices
  To get the most out of this script you should maintain these things.
  * Don't use HEADLESS mode. Because no IP leak prevention, fingerprint defending, etc. can be done in headless mode.
  * Youtube doesn't count views from the same IP after a certain time. Like, don't expect to get 100 views from 10 proxies. If you want more views, try to use a lot of premium proxies(free proxies are flagged by most websites). DO NOT use TOR proxies.
  * Use both [urls.txt](https://github.com/Tiago08/YouTube-Viewer#urls) and [search.txt](https://github.com/Tiago08/YouTube-Viewer#search)
  * And use as many [urls](https://github.com/Tiago08/YouTube-Viewer#urls) and [keyword::::title](https://github.com/Tiago08/YouTube-Viewer#search) as you can. Don't use just one video.

