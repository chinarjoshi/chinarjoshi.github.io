---
title: "Portfolio"
layout: single
toc: true
toc_label: "Navigation"
read_time: true
author_profile: true
permalink: /portfolio/

header:
  overlay_color: "#000"
  overlay_image: /assets/images/code.jpg
  overlay_filter: "0.5"
  
iotools:
  - image_path: /assets/images/iotools-nb.png
    alt: "IoTools Logo"
    title: "IoTools"
    excerpt: "Intuitive tools for managing internet of things applications"
    url: "https://chinarjoshi.com/IoTools/"
    btn_label: "Product Page"
    btn_class: "btn--primary"
    
mediamatch:
  - image_path: /assets/images/blur-code.png
    alt: "MediaMatch Logo"
    title: "MediaMatch"
    excerpt: "Share media reccomendations with friends and family"
    url: "https://chinarjoshi.com/mediamatch/"
    btn_label: "Product Page"
    btn_class: "btn--primary"

visual-aid-transducer:
  - image_path: /assets/images/vat.png
    alt: "Visual Aid Transducer Logo"
    title: "Visual Aid Transducer"
    excerpt: "Navigate the world with haptic feedback"
    url: "https://chinarjoshi.com/visual-aid-transducer/"
    btn_label: "Product Page"
    btn_class: "btn--primary"
    
pico-and-goliath:
  - image_path: /assets/images/goliath.png
    alt: "Pico and Goliath Logo"
    title: "Pico and Goliath"
    excerpt: "A fast pased competitive 2-player arcade game"
    url: "https://chinarjoshi.com/pico-and-goliath/"
    btn_label: "Product Page"
    btn_class: "btn--primary"

covid19-date-selector:
  - image_path: /assets/images/virus.png
    alt: "Covid19-Date-Selector Logo"
    title: "COVID-19 Date Selector"
    excerpt: "Visualize the spread of COVID-19 on a day-by-day basis"
    url: "https://chinarjoshi.com/covid19-date-selector/"
    btn_label: "Product Page"
    btn_class: "btn--primary"

ds-emacs:
  - image_path: /assets/images/ds-emacs.png
    alt: "Data Structure Logo"
    title: "Data Structure Editing Macros"
    excerpt: "Edit abstract data structures through vi-inspired commands on the terminal"
    url: "https://chinarjoshi.com/ds-emacs/"
    btn_label: "Product Page"
    btn_class: "btn--primary"
---
<style>
    blockquote {
        margin-top: 0px;
        margin-bottom: 0px;
    }
    details {
        margin-bottom: 1em;
    }
</style>

# Portfolio
These are my showcased software products. All of the projects are MIT licensed and open source on GitHub; if you're interested, contributions are always welcome!

## Ongoing
Projects currently in progress ❯

### IoTools
_Intuitive tools for managing hobbyist internet of things applications_

> Because not all IoT apps need a machete; some only need a chef's knife

Most internet of things platforms are overkill for non-industrial applications. IoTools serves to provide functionality somewhere between Google Cloud IoT and a personal flask server. IoTools is a one stop shop for communicating to your IoT device, collecting data through HTTP requests, and identifying trends in your data.

<details>
    <summary>
        Read more
    </summary>
    <small>
        IoTools will be deployed to iotools.cc upon completion. You can track its progress at its <a href="https://github.com/chinarjoshi/iotools">GitHub page</a>.
    </small>
</details>

{% include feature_row id="iotools" type="left" %}

### MediaMatch
_A platform to share media recommendations with friends and family_

It's such a common occurance to want to share a movie or tv show with a friend or family member, yet messaging and social media apps don't have adequate functionality for it. MediaMatch aims to provide an intuitive, consistent, and powerful interface to share all forms of media on a single platform.

<details>
    <summary>
        Read more
    </summary>
    <small>
        MediaMatch will be deployed to mediamatch.cc upon completion. You can track its progress at its <a href="https://github.com/chinarjoshi/iotools">GitHub page</a>.
    </small>
</details>

{% include feature_row id="mediamatch" type="left" %}

## Completed
Projects that have been completed ❯

### Visual Aid Transducer
_Navigate the world with haptic feedback_

The Visual Aid Transducer (VAT) is a wearable gadget that transduces the distance of obstacles to haptic feedback in order to better visualize one's surroundings. The VAT consists of an Arduino circuit, 3D printed cast, and program to operate the ultrasonic sensors.

<details>
    <summary>
        Read More
    </summary>
    <small>
        This project was submitted to <a href="https://lemelson.mit.edu/inventeams">MIT InvenTeam</a> and placed semifinalist.
    </small>
</details>

{% include feature_row id="visual-aid-transducer" type="left" %}

### Pico and Goliath
_A fast paced competitive 2-player arcade game_

The objective of the game is to hit the ball into the opponent's moving goal 3 times. The combination of the two starkly different character paradigms combined with an innovative physics engine allows for very rich gameplay with a high skill-ceiling. The game is built with PyGame, a python wrapper for the SDL library.

<details>
    <summary>
        Read More
    </summary>
    <small>
        This project won first place at <a href="https://www.fultonschools.org/techcompetition">Fulton County Tech Competition</a> in Digital Game Design.
    </small>
</details>

{% include feature_row id="pico-and-goliath" type="left" %}

### Covid-19 Date Selector
_Visualize the spread of COVID-19 on a day-by-day basis_

This is a web API to allow the user to visualize a snapshot of the COVID-19 situation in the USA on a specific day. The user can see exactly how many cases there were in a specific county in this snapshot of time. The frontend is built with the Dash framework.

<details>
    <summary>
        Read More
    </summary>
    <small>
        This project was submitted to <a href="https://hacklytics.io">Georgia Tech Hacklytics</a>. The map generator is built with the Plotly Express library.
    </small>
</details>

{% include feature_row id="covid19-date-selector" type="left" %}

### Data Structure Editing Macros
_Edit abstract data structures through vi-inspired commands on the terminal_

This command line utility implements two essential data structures, trie and hash-table, in an easy to grok implementation. The program does not rely on the standard template library, so it demonstrates dynamically allocated memory without being cluttered with complex structs.

<details>
    <summary>
        Read More
    </summary>
    <small>
        <code>data</code> is the binary file compiled with <code>g++</code>, and the Makefile instructions can be found in the <a href="https://github.com/chinarjoshi/DS-Emacs/blob/main/Makefile">Git repository</a>
    </small>
</details>

{% include feature_row id="ds-emacs" type="left" %}
