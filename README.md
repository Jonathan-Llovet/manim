# Opening Questions Manim

## About
Code for videos on the [Opening Questions](https://www.youtube.com/channel/UCRQ5gGxixCkYamF5S3sU1hA) Youtube channel.

Opening Questions is here to make resources for people to learn and engage with computer science, programming, math and science (and how they have developed throughout history), and philosophy.

Projects with source code will have links to their own repositories.

Animations can be found in [opening-questions-manim/opening\_questions](https://github.com/Jonathan-Llovet/opening-questions-manim/tree/master/opening_questions)

The animations are made with the manim math animation engine, which was originally made by Grant Sanderson for 3b1b. Many thanks to Grant for creating this powerful tool, sharing it with the world, and making videos that help us see what's wonderful about math.
You can find the original manim repository here:

- [3b1b/manim](https://github.com/3b1b/manim)
I have included extensions of manim provided by the community. Many thanks to Alexander Vázquez (Elteoremadebeethoven) for being so helpful with learning manim and supporting the community.

## Usage
I recommend using docker-compose to run manim. This simplifies the otherwise difficult installation process, and it helps prevent potential conflicts between dependencies here and other applications on your workstation.

### Install Docker
If it is not already installed, you'll need to [install Docker](https://docs.docker.com/get-docker/).

---

### Create .env for Environment Variables
Following this, create a file `.env` in the root of the project (i.e., `manim/.env`).
- This will contain environment variables for your manim container.

In `.env`, specify the `INPUT_PATH` that contains the Scenes that you want to render.

```INPUT_PATH=/Users/me/manim/```

Then specify the `OUTPUT_PATH` that will be the output directory for artifacts created by manim.

```OUTPUT_PATH=/Users/me/manim/outputAnimations/```

The `INPUT_PATH` and `OUTPUT_PATH` environment variables that you specified in `.env` are used to create volumes between your host machine and the docker image, which will allow docker to read and write files to and from your host machine in the mapped directories.
    - See [this page](https://docs.docker.com/storage/volumes/) for more information about volumes in docker.

---

### Building a Manim Docker Image
Following this, inside the `manim` directory, run the following:
```shell
docker-compose build
```

This will generate a docker image that you can render your scenes in.

---

### Running Manim
Finally, you can render your scenes in manim. Try one of the example scenes or one from opening_questions:

WarpSquare Scene:
```shell
docker-compose run manim example_scenes.py WarpSquare -l
```

Custom Example Scene:
```shell
docker-compose run manim opening_questions/learning_manim/learning_manim_001.py Shape -l
```

Syntax: 
```
docker-compose run manim <relative_path_to_scene>.py <classname> [flags]
```


## Resources
### Resources for Learning Manim
- Elteoremadebeethoven
    - [Manim Tutorial Youtube Series](https://www.youtube.com/watch?v=ENMyFGmq5OA&list=PL2B6OzTsMUrwo4hA3BBfS7ZR34K361Z8F)
    - [Animations With Manim](https://github.com/Elteoremadebeethoven/AnimationsWithManim)
- malhotra5
    - [Manim-Tutorial](https://github.com/malhotra5/Manim-Tutorial)
    - [Manim-Guide](https://github.com/malhotra5/Manim-Guide)
- [Euler Tour, a web based sandbox for manim](https://eulertour.com/lab/example_scenes)
- [Guided Tour from Talking Physics](https://talkingphysics.wordpress.com/2019/01/08/getting-started-animating-with-manim-and-python-3-7/)
- [Manim Documentation](https://manim.readthedocs.io/en/latest/index.html) (In Progress - Please contribute!)
- [Reddit/r/manim/](https://www.reddit.com/r/manim/)

### Related Projects
- [Manim.js](https://github.com/JazonJiao/Manim.js)
- [Primer](https://github.com/Helpsypoo/primer)

### Other Animation Tools
- [Unity](https://unity.com/)
- [Blender](https://www.blender.org/)
