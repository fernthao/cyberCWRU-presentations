# DVWA!
## Let's put our skills to the test

<!-- .slide: data-background="backgrounds/image1.svg" -->

---

## Installing Docker

<!-- .slide: data-background="./../backgrounds/image2.svg" -->

This varies depending on your package manager!
Since a lot of you will have debian/ubuntu/kali, run:

```bash
sudo apt install docker.io
```

---

## Basic Setup
<!-- .slide: data-background="./../backgrounds/image3.svg" -->

We would rather run docker in rootless mode!

Here is a [tutorial](https://linuxhandbook.com/rootless-docker/)

---

## Pull the DVWA image
<!-- .slide: data-background="./../backgrounds/image4.svg" -->

```bash
docker pull vulnerables/web-dvwa
```

---

## Run the DVWA Container
<!-- .slide: data-background="./../backgrounds/image2.svg" -->

This will be hosted on localhost at port 80
```bash
docker run --rm -it -p 8080:80 vulnerables/web-dvwa
```

---

## Login to DVWA
<!-- .slide: data-background="./../backgrounds/image3.svg" -->

Username: `admin`
Password: `password`

Reset the database after logging in and log in again to get started!

---

# Hacking Time
<!-- .slide: data-background="./../backgrounds/image4.svg" -->
