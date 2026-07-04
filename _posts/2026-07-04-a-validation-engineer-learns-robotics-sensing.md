
---
layout: post
title: "A Validation Engineer Learns Robotics Sensing — In Public"
---

I've spent my career so far as an analog validation engineer. My days are spent characterizing ADCs, DACs, and LDOs — measuring noise floors, hunting down non-linearities, finding the corner cases where a chip's real behavior drifts away from its datasheet. It's careful, skeptical work. You learn to trust nothing until you've measured it yourself.

Now I'm pointing that same skepticism at a new target: robotics sensing. Specifically, the sensors that let robots *touch* — force sensors, tactile arrays, the whole emerging field of robot skin. Over the next several months, I'm learning this field from the ground up, and I'm going to document all of it here: the experiments, the data, the mistakes, and the honest cost of doing this outside a professional lab.

## Why robotics sensing, and why tactile?

The robotics industry is in an interesting place. Humanoid robots and advanced grippers are moving from research labs into real products, and they all share a problem: to manipulate objects reliably, a robot needs to *feel* — how hard it's gripping, whether an object is slipping, what texture it's touching. That's tactile sensing, and it's one of the younger, less-settled corners of the sensor world.

Here's what struck me when I started reading into it: a tactile sensor is, at its heart, a resistive or capacitive element feeding an analog front-end feeding an ADC. Bridge circuits, low-noise amplification, careful excitation, noise characterization — this is the exact discipline I already practice, just pointed at force instead of voltage. I'm not starting from zero. I'm redirecting.

## The plan

Over roughly the next six to nine months, alongside a full-time job:

1. **Build a home characterization rig** for around ₹5,000–6,000 — a 24-bit ADC module, calibrated weights as a force standard, and a lot of methodology borrowed from my day job. No oscilloscope, no bench DMM, no lab-grade anything. Part of the experiment is finding out how far cheap hardware can go when the methodology is sound.
2. **Properly characterize a ₹150 force sensor** — sensitivity, linearity, hysteresis, drift, temperature dependence, response time. Not "I wired it up and it works," but real metrology with error bars and honest uncertainty analysis.
3. **Learn estimation and filtering** — Kalman filters applied to my own sensor's noisy data, not textbook examples.
4. **Build a haptic device** — Stanford's open-source Hapkit, sourced with Indian suppliers and substitutions.
5. **Finish with a capstone**: a small tactile sensor array with a readout front-end I design myself, characterized channel by channel like an IC, feeding a small machine-learning classifier for touch and slip detection.

Every one of those steps will become one or more posts here, with the data and code published alongside.

## What makes this blog different

There is no shortage of sensor tutorials online. Wire this to that, upload the sketch, done. What's genuinely hard to find is anyone treating cheap sensors with real measurement discipline — qualifying the instrument before trusting it, quantifying hysteresis instead of ignoring it, publishing error bars instead of a single suspiciously clean curve.

That discipline is the one thing I can offer that most hobby content can't, because it's what I do professionally. So the rule for this site is simple: **nothing gets stated here that I haven't measured, and every measurement comes with its uncertainty.**

The flip side: in robotics itself, I'm a genuine beginner. I'll get things wrong. When I do, the mistake stays in the post — struck through, explained, learned from. In validation work, the failures teach you more than the passes. I expect learning in public to work the same way.

## What's coming next

The first real post will be the characterization rig itself — the full parts list, what each piece costs in India, and the step I suspect most hobby setups skip entirely: qualifying the measurement chain before measuring anything with it. Can a ₹2,000 ADC module be trusted? There's exactly one way to find out, and it involves measuring the measurer.

If you're an engineer curious about robotics, a robotics person curious what a validation mindset looks like, or someone in India trying to do serious sensor work on a hobby budget — stick around. The RSS link below will bring each new post to you.

Let's measure some things.
