# CART-470-Personal-Project-Journal
This is the project journal for CART 470.

### Journal Entry Week 2

&emsp;Our project - an interactive soundscape to explore the Concordia campus - has begun relatively smoothly. Since we have not yet met with our client, Florian Grond, the vision for what the final product will look like is a little vague and varies slightly between each of my team members. For example, the project brief describes select points of interest around the Concordia campus wherein the soundscape experience would occur, but some group members believed travelling between points of interest should happen within a 3D space, whereas others (me included) believed these locations should be navigated via the campus map. Hopefully, after meeting with Professor Grond, our differing visions will converge, at least temporarily. 

&emsp;Looking into the resources available, as well as the resources given by the great guest speaker, Professor Grond, and some classmates, it has become clear that our project won’t be built from the ground up but rather would be more of a cohesive organization of various assets (topolocal maps, floor plans, immersive audio). We initially saw this project as a grounded, straightforward tour of the school; however, after our presentation, we realized it can be much more creative and abstract than we planned. It is an art project, after all. Furthermore, we have since realized that aiding the visually impaired should be incorporated into our design.

&emsp;Regarding the work we have done in preparing to meet the client, our group has gathered some background data about Concordia’s campus, finding a floor map of one of the buildings which includes a 360-degree view of one of the rooms (found at https://www.concordia.ca/hospitality/venues/concordia-conference-centre/main-floor-plan-seating-capacity.html). We also formulated some questions, created a Photoshop mock-up of the basics of the project, and coordinated a Discord server and Fizzy board.

<picture>
 <img src="CART 470 Initial Prototype.png">
</picture>


### Journal Entry Week 3

&emsp;The meeting with Professor Florian Grond went very well. It lasted about an hour, and in that time my team and I were able to get a much better picture of Professor Grond’s vision. He emphasized many of the aspects we should prioritize, particularly how this project should be accessible to individuals with visual impairments and how we should simulate the Concordia campus so that they could better experience it via immersive 3D audio. 

&emsp;During this conversation, Professor Grond mentioned numerous pieces of technology that he expects us to use, such as a specialized multi-channel microphone for sound, a 360-degree camera available at the CDA (or a simple cell phone panorama) for the visuals, and audio software like Eclipsa and IAMF for sound configuration. One key detail we learned was how we were expected to record the audio ourselves, which went against our initial assumption that the audio would be provided (as stated in the brief). Managing surprises like this is important in project development, so we adjusted our timeline to give us time to record audio before embarking on the rest of our tasks. Luckily, we are still in the research phase, so this adjustment was very minor.

&emsp;Regarding research, my team and I have split up research responsibilities so that each of us would take time to become better informed about these new technologies. I took up the map navigation feature and looked into how to access the Google Maps API, how we can utilize Google Street View vs. the regular map, and what it would take to integrate these features into a custom-built website. From what I’ve deduced, the Google Maps angle is our best bet for traversing the Concordia campus across downtown Montreal, but would be insufficient to navigate within each Concordia building. For that, we would need to access floor plans, which should be available upon request. We also learned that, in terms of taking artistic liberties, he would prefer for this project to be more straightforward than abstract.


### Journal Entry Week 4

&emsp;This past week, our group divided up work based on our particular skill sets. Daniel experimented with implementing location-based sound in a 3D space; Andre worked with a 360-degree camera to capture a navigable immersive space; Jeboy and Willy conducted further research on alternate approaches to our project; and I began working on a website layout using Figma. Since building a platform to connect all the different pieces of data is as important to Mr. Grond as the data itself, our group has placed an emphasis on the web-development side of this project. This past week, I embarked on a crash course to learn the Figma software, then drafted designs for the landing page, map page, and the soundscape page, basing the styling on Concordia’s official website - mirroring the font types, colors, and layout. Delving past the superficial elements, I also began brainstorming ways to make our website more accessible for those with visual impairments. Simplicity and visual clarity are key design philosophies of our website, and we aim to add features such as a colorblind mode and voiceover audio for the important information (such as the location names when navigating the map).

&emsp;In addition, my team and I met with Mr. Grond over Zoom to share our progress and discuss how it aligns with his vision. He seems very pleased with the work we have so far and has conveyed how our current efforts align with his vision, but has expressed that we should focus more on integrating higher-order ambisonics rather than our current, much more basic sound files. As a group, our primary goal is to help scale up Daniel’s prototype to handle more channels for higher-order ambisonics, and to make the pivot from Figma prototyping to actual web development programming in Visual Studio Code. 


### Journal Entry Week 5

&emsp;The map is a core feature of the website as it is the primary method by which users can access the visual/soundscape experiences. Furthermore, since the goal of this project is to construct an immersive audio-based experience for those who may or may not be familiar with the Concordia campus, a map is essential to bring all the audio/visual recordings together and ground them in a relative space. I volunteered to handle this portion of the project, which began with expanding the Flask-based website layout designed and developed by Andre and me, and implementing some sort of interactive map API. The most obvious choice was the Google Maps API, as it provides high-resolution maps that let users navigate the entire world, zoom in and out on specific regions, and enable complex map customization features for programmers. While many of the features fall outside the scope of the project, this API would be perfect for the Concordia Soundscape Explorer. However, further investigation of the billing information for the type of map suited for this project reveals a strict credit limit restricting our use of certain mandatory features.

&emsp;While this isn’t a deal-breaker, I decided to research various alternatives to Google Maps that would suit a prototype, eventually landing on the open-source Leaflet software (https://leafletjs.com/index.html), which does not require an API key and offers all of the features needed for this project, such as interactive map markers, customizable map icons, and restrictions on map boundaries and zoom levels to confine the map view to the Concordia campus. The main trade-offs compared to the Google Maps API are a lower map resolution, constrained map modifiability (no option to disable store names, street numbers, traffic lights, etc.), and map markers are not fixed in the same location if the user zooms the map. My temporary solution to the latter problem is to simply disable zooming, though zooming would be a great feature to keep in the final product. On a positive note, the main functionality of clicking on icons to transfer to the “Explore” audio-visual page works. Once the database gets set up, each of these markers will contain an audio and image ID that will be sent to the “Explore” page, allowing that page to populate its contents based on specific soundscape assets stored in MongoDB. This code was uploaded as a branch to our GitHub repository.

&emsp;Once the map is refined, Professor Grond has given us advice on how to tailor the map to users with visual impairments who don’t rely on a mouse cursor to navigate. He advised us to create a list of the locations alongside the map (corresponding to the same markers) that users can navigate through using arrow keys, which will read out the name of that location and enable users to access its unique “Explore” page. Implementing these features is next on my list of priorities after finalizing the map.

<picture>
 <img src="CART 470 Map Page V1.png">
</picture>

<picture>
 <img src="CSE Github Repository.png">
</picture>


### Journal Entry Week 6

&emsp;This past week, I spent much of my time modifying the Leaflet API to fix notable map bugs and create popup windows for each point of interest that include a preview of the location, its name, a static image, and a link to the actual soundscape page. 

&emsp;As I mentioned in my previous journal entry, the most notable fault with the map is the map markers, which were not fixed in place. The previous version of the map created inconsistencies with the markers' positioning across different browsers. This was especially notable with the intersection markers, which were correctly displayed on the street on Firefox, yet located on top of buildings on Safari. This problem is exacerbated by the zoom levels, which caused the markers to drift from their initial positions. The solution was an issue with the anchor point and required manual adjustment to ensure the markers remain in place.

&emsp;With this error fixed and the zoom functionality enabled, I continued working on enhancing the flow between clicking on a marker and navigating to the soundscape explorer page. Previously, clicking on the marker would navigate directly to that page, but we decided as a group that showing a preview of each location would be much more intuitive. Fortunately, Leaflet provides a popup mechanism that can display text when a marker is clicked. Modifying this feature with basic JavaScript, I was able to change the code so the popups appear when the user hovers over the markers, and then began structuring an HTML template for the locations to display key information. As stated, previews will contain the location’s name, a static image, possibly a brief description, and a button that links to the soundscape page. These buttons will be unique for each location and send an identifier to the soundscape page, so that it can fetch that specific location’s data (sound and visuals) from the database to fill out the page. Our team still needs to gather materials and structure the database by location ID, so the buttons only provide a basic link for now.

&emsp;Unfortunately, we were unable to meet with Professor Grond for this class due to him feeling unwell, but we have reached out for input and are awaiting a response. Our next steps as a team are to record data, fill out the database, implement the ambisonics in HTML, and work on our midterm presentation.


### Journal Entry Week 7






### Journal Entry Week 8






### Journal Entry Week 9






### Journal Entry Week 10






### Journal Entry Week 11






### Journal Entry Week 12
