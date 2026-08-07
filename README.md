# using HomeBox for home inventory
## motivation
i just graduated college and am now crashing on my parents' couch in small 1bed/1bath condo. there isn't nearly enough space for all my things because i consumermaxxed all throughout college and have amassed more belongings than my whole family combined. i need to put all my stuff in storage totes in a leased storage space.

### previous workflows
moving from apartment to apartment in college. i would simply put my stuff in a cardboard boxes, write down the category of the box (ex: kitchen), and jot down the individual elements. however, this isn't optimal because i 
  1. don't want to have carry around a notebook to add/look up items
  2. don't want to write down items with pen/paper (i can type pretty fast 😎)
  3. need something where i can quickly search for the item i need

**the next path forward is to track everything digitally**
## enter homebox
i initially planned on just vibe-coding a basic front end for this app and deploying on a serverless platform like Vercel or Netlify and calling it a day. that was until i stumbled upon a HomeBox, a FOSS application for this exact purpose written in Go. i love creating my own solutions for things but only out of necessity. so if something already exists and it works good, i'm using that. i'm not going to reinvent the wheel.

**deployment?**
i could still deploy my homebox setup into a serverless platform, however, i already have a Tailscale tailnet setup with some running servers. also, it seems like self-hosting is what the cool kids are doing so why not use what i already have and give it a shot

## getting started with HomeBox
per the docs, the preferred installation is installing a docker container. i took me until now to realize that i have to have docker desktop running in macOS for containers to run or else i would get a  `docker daemon error`. first roadblock. i try to avoid GUIs where i can. it's counterintuitive to have a desktop application open in the background to use docker in my terminal.

thankfully, [Colima](https://github.com/abiosoft/colima), takes care of this. setup is super simple
```
brew install colima docker docker-compose
docker context use colima
```
and now we can run the docker container without docker-desktop. goodbye menu-bar icon.

<img width="328" height="387" alt="Screenshot 2026-08-07 at 3 11 28 PM" src="https://github.com/user-attachments/assets/2072afad-0d51-47fc-9727-ff9d22a50c51" />





