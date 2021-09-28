Regardless of if students pass the checkpoint or not, please provide actionable feedback to them to help them improve or to give them guidance on what they need to work on to pass next time.

The student is asked to submit answers to questions about meetup.com's API docs.

> Visit the meetup.com API docs found here: [https://www.meetup.com/meetup_api/](https://www.meetup.com/meetup_api/). Answer the following questions:


> 1. Does this API require authentication?

Yes.


> 2. Find the upcoming events search endpoint documentation at https://www.meetup.com/meetup_api/docs/find/upcoming_events/. Spend a full minute or two reading over the spec and building a mental model of what the JSON returned by this endpoint would look like. 
>  Is there a `radius` property in the request parameters? 

**YES** 


> Which field would give you a description of an individual event? 

Any of `event.description` or `event.plain_text_description`, `event.plain_text_no_images_description`. 

> 3. Describe the rate limiting policy.

https://www.meetup.com/meetup_api/#limits - API will warn and throttle, you have to respond. Doesn't have a specific, explicit number indicated. You "tune" to their responses.

> 4. What are some errors you might expect to see when calling this API?

https://www.meetup.com/meetup_api/#errors 

- 400 Bad request when there was a problem with the request
- 401 Unauthorized when you don't provide a valid token
- 429 Too Many Requests when you've gone over your request rate limit
- 500 Internal Server Error 

