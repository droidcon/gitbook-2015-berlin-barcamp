# Android Template Project - Eugen Martynov

## Why?

The idea to have project that is ready to clone and prototype. It is buildable, testable and understandable.
More beyond it is on going documentation where we share stable dependencies, common components (Licences activity), latest findings for automation, etc.

## General thought about project

 * The project start should be matter of seconds or minutes - check out, import to studio, run gradle. The first run require internet connection and time to download and install dependencies
 * The central point is gradle files. Everything that you're doing should be automated, downloaded, installed and available via gradle tasks
 * Project should be self contained  - code convection, documentation, acceptance test should be part of project 
 
## Current support tasks from gradle
 * Assembling (with obfuscation and signing)
 * Unit testing with code coverage
 * Uploading to hockeyapp
 * Localisation
 * Jenkins jobs manipulaions
 * Dependcies versions check
 
## Additional scripts

Our branching model is Gitflow. For every feature branch we use `gradle-jenkins-plugin` for creating/ updating and deleting jenkins job.
We use custom way of working with translators (we know about services that make you life easier). So we have own ruby script to generate strings and it is wrapped in gradle with jruby plugin (you don't need to install ruby or gems manually, it will be done by gradle plugin).
We distribute build to our QA and beta community through HockyApp. We use hockeyapp plugin to automate it.
We work in scrum and every iteration start we update our dependencies to have time verify them. We use `gradle versions` plugin to automate report about updates.

## Overview

The minimal setup contains three modules - java library, android library, android application. App module depends on libraries, and android library has only dependency to java library. Java library is core functionality and should not have any notion about environment and implementation details.

Plugins definition and all depencnies versions are specified in roo project `build.gradle`. There also application of common plugins for projects - dependency checks and code coverage. `gradle.properties` is used only for gradle run parameters - daemon and parallel build for us.

Code also holds our pattern for our logic separation (Presenter, View, ModelView, wire within Activities and Fragments).

### Current setup
 * Java 7
 * Gradle 2.4
 * Android gradle plugin 1.2.3
 
### Dependency Injection
 * Dagger 2
 
### Testing
 * Robolectric 3
 * Mockito
 * Android AssertJ
 
### Other
 * OrmLite
 * EventBus
 * Android Annotations (we use them a lot)
 * License dialog (we partialy use it)
 
## Future
 * Add acceptance tests (calabash, gradle tasks)
 * Migration to announced new android tools (android gradle plugin 1.3)
 * Speed imporvements over modules pre-dexing
 * Java 8 with RetroLambda
 
## Idea in review 
 * Kotlin
 * Groovy
 
## Where can I get it
It is not public right now but should be soon. Please drop me email and I will update you.

###Contact
 * @jack_martynov
 * https://github.com/emartynov
 
 




