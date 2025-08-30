+++
title = "Kloudtech OJT Recap"
date = 2025-08-04
updated = 2025-07-04

[taxonomies]
tags = ["Internship", "Electronics"]

[extra]
social_media_card = "card.png"
+++

This blog post is a personal recap of my internship at Kloudtech. It’s part of my ECE training and something I want to share to look back on later. I also hope it gives other students an idea of what it’s like to intern in a tech company, especially if you’re into embedded systems.
<!-- more -->

## What is Kloudtech?

Kloudtech is a company that builds embedded systems and IoT devices. One of their projects is called Kloudtrack, which collects data from sensors and sends it to the cloud through WiFi or GSM. These devices are actually deployed in different parts of Bataan and are used to monitor real-world conditions like weather.

I chose Kloudtech because I’ve always been interested in embedded systems and how hardware and software come together. I had already heard about Kloudtrack before, so I was curious to learn more about how it works behind the scenes. I also wanted to improve my practical skills and understand how real products get built.

The topics in Kloudtech’s work are very connected to what we study in the classroom. We used microcontrollers, sensors, communication protocols, PCB design, and even 3D modelling. It’s one thing to study these in class, but seeing them used in a real company made them more meaningful.

## Interview and Onboarding

The interview was done onsite; I was nervous but excited. I talked about my background, my past projects, and why I wanted to intern at Kloudtech. They asked me some technical questions, which I think I handled well. After a few days, I got the good news that I was accepted!

The onboarding process was smooth, and I was introduced to the site, the team, the projects, and the tools we would be using.

Due to my relocation issues, I had to do my internship remotely, and I'm grateful that Kloudtech allowed me to do this. I was given access to the necessary tools and resources, and I was able to communicate with them through Google Meet and Messenger.

This was a bit challenging at first, since there is a communication barrier when you’re not physically present. Additionally, I didn't have direct access to all the hardware, making verifying if the code still works almost impossible. However, I'm glad that I had mentors who guided me through the tasks and answered my questions.

## Training

In the first week, I focused on learning more advanced C++. I already knew a bit of the basics, so I jumped into object-oriented concepts like classes, inheritance, and polymorphism. I also explored C++ libraries for strings, time, math, file handling, and JSON. Since we worked with ESP32, I also reviewed its limitations and best practices.

In the second week, I added CI to the codebase so that every commit would automatically be checked. This helped avoid broken builds. I also documented how to build and upload the firmware using flags like `USE_GSM`, APN settings, and station codes for Bataan. Then I started refactoring the code into modules like `BaseClient`, `GsmClient`, `SdCard`, and `SensorManager`.

On the third week, I worked on the Kloudtrack-Cloud project, which connects to AWS. I added CI again and refactored the structure using object-oriented programming. I added new modules and wrote documentation for how to build and upload. We also had a team alignment meeting where we shared updates.

During the fourth week, I experimented with MQTT and AWS IoT Core. I ran tests on ESP32 to send and receive data using MQTT. I also played with the AWS dashboard to simulate commands. Around this time, I started testing out Rust because it's not me without the blazingly fast and memory-safe Rust. I also started learning KiCAD for PCB design.

The fifth week was mostly focused on PCB work. We used KiCAD to design schematics and lay out a simple PCB. I practiced placing components and routing connections to keep the board clean. I also looked deeper into low-level Rust using `no_std` and attended a session on 3D modeling using Autodesk Inventor.

In week six, I designed a small keychain using Inventor with my logo and Kloudtech’s. I also learned about multitasking on the ESP32 using FreeRTOS. I tried out `vTaskCreate`, queues, mutexes, and semaphores. I saw how the ESP32 can run tasks on multiple cores, and how to manage them without causing bugs. I also cleaned up my PCB design by adjusting the routes.

During this stage, it was helpful that I had experience with multi-threaded environments in Rust, as it made understanding the synchronization primitives and task management in FreeRTOS easier.

In the final week, I mostly spent time writing documentation, final reports, and reflecting on everything I learned. It wasn’t the most exciting part, but it helped me see how far we’ve come.

## Key Takeaways

Here are some of the most important things I learned during my internship:

- How to write cleaner and more modular C++ code for embedded systems
- How to work with AWS IoT Core and send data using MQTT
- How to use PlatformIO as a better (more flexible) alternative to the Arduino IDE
- PCB design using KiCAD
- Basic 3D modeling with Autodesk Inventor
- How multitasking works on the ESP32 using FreeRTOS
- That debugging in real-world setups takes patience, trial and error, and clear thinking
- The value of writing documentation, even if it's not the most exciting part
- How important teamwork, communication, and attitude are in any work environment

## Acknowledgment

Before I end this post, I want to thank everyone who helped me during this internship.

Thank you to Engr. Gelvoleo for guiding me throughout the internship. I learned a lot from your support and feedback.

Thanks also to Mr. JC Ilano for the advice and encouragement, and to Mr. Casana and Mr. Raymundo for helping me during onboarding. I really appreciate the help.

To the rest of the Kloudtech team, thank you for making me feel welcome even while working remotely.

Lastly, thank you to my co-interns for the teamwork and shared experiences that made the internship more fun and meaningful.

## Closing Words

Looking back, I learned a lot during this internship. I’m really grateful for this opportunity, and I hope to keep building on what I’ve learned.

I'd like to add that I maintained a minimal amount of pictures to ensure I'm not disclosing sensitive information.
