#AI Video Spaceport
## Artist Statement/ Inspiration
So for generating video, since AI is being used to generate the images it made me think of technology and it’s role moving forward. I also have another project, Starlight Repairs, I’m working on that involves a spaceport on the water so I figured it would be a fun place to start as well as a way to generate ideas for the other project. I was hoping to demonstrate a transition between places that I planned on being present in the project. The main areas I wanted to include was the spaceport on the water, the mechanic shop, and the view of ships in from a sort of news screen.  
A large inspiration for this was shows that treat space as a sort of sci-fi that is rough around the edges. For example, Star Wars, Cyberpunk and Firefly. Cities being large and sprawling but also having areas that are run down or have been scrapped and modified to suit new needs. I figured that kind of setting fit well with the wild west state of AI generation as it is right now. There is also a YouTube called Doctor Diffusion who does generations with Disco Diffusion and explanations of settings that I found useful and gave me ideas a couple modifications for prompts.

## Methods
For the generation of the video I used Disco Diffusion v5.7, linked below.
https://colab.research.google.com/github/alembics/disco-diffusion/blob/main/Disco_Diffusion.ipynb
For the most part I used standard settings and ran each cell of the collab notebook in order. The most notable changes occurred in a couple places. In ‘3. Settings’ I changed batch name to closer suit the topic, just naming it spaceport, then I changed the steps from the default 250 to 110. 
I did a short render using 150 steps and I felt is was more detail then needed and a run I did with 80 steps left a lot of blank space, not defining as much from the noise. In addition I also made the frame size a 512x512 to make the video into a square, though I also thought using that as a standard might make an interested animated texture inside unreal at some point in the future. 
In step ‘4. Animation’ the most notable change made was making the animation_mode into 3D, changing the max frames to 800 since I only wanted to run a minute or so at around 12 frames a second. Then rotation_3d_z was changed from 0 to 2 so there would be a slight spin on the transitions. I also enabled turbo_mode in hopes of speeding up the process.
I feel like I could have tried changing a few more aspects of the animation in particular because even with smaller frames, less steps and turbo mode frame generation still occurred pretty slowly, which caused a bit of issues down the line, which I’ll talk about briefly a bit later. 
After adjusting all the settings as I wanted, I added 3 text prompts for diffusion to use, with frames 0, 50 and 100 where transitions should be occurring. The specific prompts used are as follows.
text_prompts = {
    0: ["A run down space port on the water with mechanical objects scattered around, digital art, 3D render", "turquoise color scheme"],
    50: ["A robot doing repairs on itself in a workshop, digital art,  3D render","pink color scheme"],
    100: ["large flying ships with Flickering screens filled with code in a dark room, digital art,  3D render","blue color scheme"],
}
A common problem I ran into was that I could only render around 100 frames before the collab notebook would kick me/stop running. After around the 4th time starting up a render I also couldn’t really use GPU anymore because of limits on google collab notebooks so I couldn’t really render effectively anymore. I took what I could and interpolated and looped it to have something close to what I wanted to produce originally. Some notes I would have liked to change is messing with the last prompt a bit more and  possibly adding a couple more frames and a spin that could time better with a loop.
I had some trouble rendering the video from the notebook as well so I took the image sequence and rendered it out in premiere and a reverse to have it be more of a loop effect. 

Google Collab Link I worked From: https://colab.research.google.com/drive/1dHbw7giGLsZ1GVzdCCZ5L5MD0coOHWV0?usp=sharing

YouTube Video Link of AI video:
https://youtu.be/uhARb6iGNoQ
w/o loop: 
https://youtube.com/shorts/Oggmc7Vr3sw

Artist Statement:
https://youtu.be/wFRiwxonvIc
