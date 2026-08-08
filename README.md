# using HomeBox for home inventory
<div align="center">
  <img width="275" height="194" alt="messyStorage_compressed" src="https://github.com/user-attachments/assets/5986d024-0dd6-4aec-8419-5c067e503f7c" />
<img width="236" height="212" alt="image" src="https://github.com/user-attachments/assets/585d6f17-1598-4252-bbf5-01a4a113679b" />
</div>


## motivation
i just graduated college and am now crashing on my parents' couch in small 1bed/1bath condo. there isn't nearly enough space for all my things because i consumermaxxed all throughout college and have amassed more belongings than my whole family combined. i need to put all my stuff in storage totes in a leased storage space.

### previous workflow
moving from apartment to apartment in college. i would simply put my stuff in a cardboard boxes, write down the category of the box (ex: kitchen), and jot down the individual elements. however, this isn't optimal because i 
  1. don't want to have carry around a notebook to add/look up items
  2. don't want to write down items with pen/paper (i can type pretty fast 😎)
  3. need something where i can quickly search for the item i need

**the next path forward is to track everything digitally**
## enter homebox
i initially planned on just vibe-coding a basic front end for this app and deploying on a serverless platform like Vercel or Netlify and calling it a day. that was until i stumbled upon a [HomeBox](https://github.com/sysadminsmedia/homebox), a FOSS application for this exact purpose written in Go. i love creating my own solutions for things but only out of necessity. so if something already exists and it works good, i'm using that. i'm not going to reinvent the wheel.

**deployment?**
i could still deploy my homebox setup into a serverless platform, however, i already have a Tailscale tailnet setup with some running servers. also, it seems like self-hosting is what the cool kids are doing so why not use what i already have and give it a shot

## better workflow
### with HomeBox, we can add locations (boxes) and assign them items. ex:
<div align="center">
  <img width="596" height="117" alt="image" src="https://github.com/user-attachments/assets/d51e4127-3042-48c6-87d8-6680048d4c8c" />
  <img width="598" height="431" alt="image" src="https://github.com/user-attachments/assets/92cab304-39d1-43a0-bf3b-130a7f09058c" />
</div>

### the other cool thing that HomeBox provides out of the box is QR code generation for each location
<div align="center">
<img width="835" height="420" alt="image" src="https://github.com/user-attachments/assets/4eb6085d-57ec-4823-9620-76fd1e82d09b" />
</div>
so if i am ever physically near a box and want to see what's inside (storage totes are not transparent), i can scan the qr and it will take me to this page. more later on how to to actually print this.


## getting started with HomeBox
per the docs, the preferred installation is installing a docker container. i took me until now to realize that i need to have docker desktop running in macOS for containers to run or else i would get a  `docker daemon error`. first roadblock. i try to avoid GUIs where i can. it's counterintuitive to have a desktop application open in the background to use docker in my terminal.

thankfully, [Colima](https://github.com/abiosoft/colima), takes care of this. setup is super simple
```
brew install colima docker docker-compose
docker context use colima
```
and now we can run the docker container without docker-desktop. goodbye menu-bar icon. after editing the basic `compose.yaml` file and running `docker compose up -d`. we are up and running with HomeBox.

<table>
  <tr>
    <td rowspan="2">
      <img
        src="https://github.com/user-attachments/assets/2072afad-0d51-47fc-9727-ff9d22a50c51"
        alt="bye-bye menubar"
        width="328"
      />
    </td>
    <td>
      <img
        src="https://github.com/user-attachments/assets/189b4a69-15fa-469b-95e1-54c2aa7320f1"
        alt="image"
        width="622"
      />
    </td>
  </tr>
  <tr>
    <td>
      <img
        src="https://github.com/user-attachments/assets/f424a181-6389-48db-b499-1540e7ccc019"
        alt="image"
        width="400"
      />
    </td>
  </tr>
</table>

## so how do we print the labels? 
### deploying on home server
now that HomeBox is running, how are we using it? this can't live on my macbook, so i need to deploy on a homelab i have tagged in tailscale as _optiserver_. this is just a [Dell OptiPlex](https://www.dell.com/en-us/shop/desktop-computers/scr/desktops/appref=optiplex-product-line) i got on sale off Amazon

<div align="center">
<img width="1121" height="490" alt="image" src="https://github.com/user-attachments/assets/f2c7952f-228e-49d0-97e5-c2c7b9b7b4c0" />
</div>







