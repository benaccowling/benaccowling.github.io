+++
date = '2025-01-17T10:15:15Z'
draft = false
title = 'Creating My Coding Blog With Hugo'
+++

<!-- Google tag (gtag.js) -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-6KG34X3C2K"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());

  gtag('config', 'G-6KG34X3C2K');
</script>

### Introduction

When I started thinking about creating a website to showcase my coding journey, I had no experience with HTML, CSS, or JavaScript, so I thought it would be too big a challenge to start from scratch. On the other hand, I didn’t want to have it all done for me with a website generator like Wix or GoDaddy because I wanted to gain some learning in web design from the experience.

I came upon Hugo static site generator which offers templates to start your website design but requires use of the command prompt and GitHub Pages to build and host the website, so I thought it was a happy medium. As well as this, a static website is appropriate for a blog because I do not need to add any dynamic features to my website.

To create this website, I majoritively used this YouTube guide to take me through it:

[Hugo tutorial](https://www.youtube.com/watch?v=5GnFZ8XpMak)

Because this guide was a bit old, its method of hosting on GitHub Pages was outdated, so for this part I used this video:

[GitHub tutorial](https://www.youtube.com/watch?v=zrmeOu8DYyw//)

The Hugo documentation recommended that I use Microsoft powershell as the command prompt and that I download the packages Git, Go and Dart sass for building the website. I did this using the Windows package manager ‘winget’ before downloading Hugo in the command prompt with:

`winget install Hugo.Hugo.extended`

### Creating and Configuring the Website

Still on the command prompt, I typed:

``` 
Hugo new site bencowling
cd bencowling
git init
git submodule add https://GitHub.com/luizdepra/Hugo-coder.git themes/Hugo-coder
```

This created the website directory ‘bencowling’, containing the folders needed for the website to run:

![Website Files](/static/img/website_files.PNG)

‘cd bencowling’ navigated me into my newly created directory where I used ‘git init’ to make a git repository containing the website files to allow me to host the site on GitHub later on. I then downloaded a theme From.in the GitHub page of the Hugo theme as a submodule. I chose the ‘coder’ theme because it suits my blog and it is mobile responsive.

In order to tweak the theme to suit my website, I altered my Hugo.toml to include the settings offered by the coder theme. 

![Hugo.toml](/static/img/config_file.PNG)

Altering these settings is quite self explanatory to change things like the title, front page description and profile image. For the profile image, I used the file explorer to add a photo to the static folder, where all images for the website are stored, referring to the image in the hugo.toml file as:

`avatarURL = "img/avatar.jpeg"`

### Adding a Post

To create my first blog post, I use the Hugo command:

`Hugo new content blog/visualizing-dataframes.md`

I found writing the blog post with markdown to be very easy to learn and markdown has all the features I needed to create a blog, such as tables or images when I’m trying to present data. Here is the website I used to learn how to write in markdown:

[markdown cheat sheet](https://www.markdownguide.org/cheat-sheet/)

### Hosting the Website on GitHub Pages

To start this process, I created a GitHub account called benaccowling (I added my middle name initials to differentiate between the website files and my GitHub account name) and within my account created a GitHub repository. The name of this repository is benaccowling.GitHub.io so that GitHub recognizes my username as this will be the url of the website.

To add the local files for the website in ‘bencowling’, First I had to link my computer to my GitHub account on the command line using:

```
git credential manager GitHub login
git remote add origin https://GitHub.com/benaccowling/benaccowling.GitHub.io.git
git branch - M main
git push -u origin main
```

This links the local git repository I made earlier to the online GitHub repository ‘origin’, renames this version of the files, or the branch, as main and pushes the contents of the local git repository to origin.

With the files now on GitHub, I had to tell GitHub how to deploy these files onto a website. This is quite a complicated process but luckily the Hugo documentation has a premade ‘workflows’ file which does just this. I copied and pasted the workflows file into my local ‘bencowling’ directory. I then added, committed and pushed these files to my remote repository on GitHub. Pushing the workflow file automatically starts deployment of the website.

At this final stage I got very stuck, receiving lots of error messages from GitHub. I checked if I had any typos in the names of files or repositories but they all seemed fine. I checked if I had not copied and pasted all of the workflows file, but it appeared that I had. 

Eventually I gave the error message to chatGPT and asked it to diagnose the problem. It told me that I needed to alter the Hugo version specified on the workflows file as it was wrong. I tried this and it worked instantly. I will definitely be using chatGPT for debugging in the future! Now that the website was deployed, I typed https://benaccowling.GitHub.io into google to find my new website!

### Conclusion

This was a great learning experience for starting out using new software such as git, as well as using the command line. I learned about how to use markdown, how to add new content to GitHub and how to use ChatGPT for debugging. I’m sure all of these skills will be useful in the future.