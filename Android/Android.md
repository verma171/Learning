#Android

* [Activity](##activity)
* [Fragment](##fragment)
* [Context](##context)


## Activity
- what is use case of Multiple Taks in Activity ? </br> //todo

## Fragment
- [Fragment Navigation](https://medium.com/@Zhuinden/simplified-fragment-navigation-using-a-custom-backstack-552e06961257)

- [Interview Questions](https://medium.com/@Shekhar14/fragment-interview-questions-c62be4b5ef68)

## Context
- Interface which provide global information about an Application environment.
- This is an abstract class which implementation provided by Andorid system.
- It allows access to application-specifice resources and classes
- help in calls for activity-level operations such as Activity/service launching, broadcasting and receiving intents etc.

- **Application Context** </br>
_This tied with the lifecycle of the application, This can be used where you need a context whose lifecycle is separate from the current context or when you are passing a context beyond the scope of an activity._

- **Activity Context** </br>
_This context availabe in activity and tied with the lifecycle of the Activity. It should be used when you are passing the context in the scope of an activity or you need the context whose lifecycle attached to the current context._


## Architecture Patterns

- **MVC|MVP|MVVM** [MindOrk](https://blog.mindorks.com/mvc-mvp-mvvm-architecture-in-android)




