---
layout: post
title:      "MET CLI Gem "
date:       2020-03-15 04:37:46 -0400
permalink:  metcli_gem
---


[Here](https://github.com/jenleebeaver/flatiron-CLIproject) you can find the link to my first CLI gem. 


I decided to work within the open sourced [Metropiltan Musuem of Art MET Collection API](https://www.programmableweb.com/api/metropolitan-museum-art-met-collection-rest-api-v10/).  I used OO programming within Ruby to link API's to two classes of data: 1) an Art class accessing the information I decided to include such as  :title, :primaryImage, :accessionYear, :department, :culture, :dimensions and 2) an API class containing methods manipulating the data. 

Initially I had to inspect the collection at the [documentation page](https://metmuseum.github.io) and discovered that I needed a way to allow the user to access data via Object Id's.  I decided to first ask the user to search based on "culture" or the region where the art was acquired.  From here there was too much data for the user to access, so I chose to give the user a selection of 10 pieces based on the first ten object id's that the API collection grabs. 

From there the user can select a piece numbered 1-10 and will see the title, a link to the image of the art, the year acquired, department, culture, and dimensions.  After the user sees this data they can choose to discover more in that region or choose to explore another region.

I would like to further elaborate on this project by allowing the user to scroll through more pieces. 

Feel free to download and explore collections of some of the MET's art at my github link at the top!  
