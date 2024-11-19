---
title: "PotatoDB - Barcode Based Room Inventory System"
date: "2024-09-07T12:30:40Z"
draft: false
cover: 
  image: "posts/inventory-system/homepage.png"
  alt: "homepage"
  hidden: false
  hiddenInList: false
  hiddenInSingle: false
  relative: true
---

An intuitive, barcode based sqlite inventory system

# Overview

![Homepage](homepage.png)

I own a lot of stuff. This includes parts for projects, tools, clothing, and souvenirs from events. In order to save space, I own many multilevel shelves to store containers. While I've been able to standardize my storage solution, there is no easy way to keep track of everything which causes issues like double buying and general friction when trying to locate an item. This project aims to solve that problem by creating an inventory system that is as stress free for the user as
possible. 

# General Layout
Barcodes are extensively used in industry for keeping track of items. There are numerous hardware and software options for creating, reading, and manipulating barcodes making it ideal for rapidly developing an inventory system. Here is the overview of how my system works. There are two types of objects in my database, Items and Boxes. Items are individual items. Boxes are containers that are able to store Items and other Boxes. 

{{< figure src="barcodes.jpg" title="items">}}
{{< figure src="boxes.jpg" title="boxes">}}

The database structure is a tree where each object has a parent that eventually ends with the root box with null parent which is my room. When adding a new item or box, the user clicks "new item/box", enters relevant info, and clicks "create". This generates a barcode that is physically printed using a label printer. The user then puts the label on the item. In order to put an item in a box, the user scans the item's barcode then scans the barcode of the box this item is supposed to go into. This updates's the item's parent to the box's id. By scanning
items and boxes, it displays the information associated with the object as well as a list of objects contained within for boxes.

{{< figure src="details.png" title="Edit page">}}
{{< figure src="search.png" title="Search function">}}

# Thoughts

My main consideration was to make it as easy as possible to add items. I wanted minimal typing so most of the parent assignment must be handled by the scanner. During development, I thought about using existing barcodes on products instead of generating my own. I elected against this as I own duplicates of some items such as lipo batteries and need to be able to track aspects unique to each item such as charge/discharge cycles.

# Future work

This is an ongoing project. The entire codebase should probably be overhauled and many new features are in the works such as selecting multiple items, adding new parameters to the database, pushing onto server, etc. Great project and will be making updates.
