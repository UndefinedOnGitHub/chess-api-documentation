The PubAPI is a read-only REST API that responds with JSON-LD data. Our goal is to re-package all currently public data from the website and make it available via the PubAPI. "Public Data" is information available to people who are not logged in, such as player data, game data, and club/tournament information. This excludes private information that is restricted to the logged in user, such as game chat and conditional moves.

This is read-only data. You cannot send game-moves or other commands to Chess.com from this system. If you wish to send commands, you will be interested in the Interactive API releasing later this year.

To use the PubAPI:

determine the data you want, and compose the URL for it based on the endpoint URL pattern
request that URL in your browser, program, Postman, cURL, or pigeon.
enjoy the JSON happy
This page is the documentation for the PubAPI. We will edit this page to make corrections and add new documentation as the API grows. We will date these changes and report them in the CHANGELOG so that you can tell what is fresh. Please keep the comments focused on the documentation itself, and use the Club Forums to discuss suggestions, bug reports, and how you use the data!

General Use Features and Issues
The format for each endpoint will be different, and described in a release note about that endpoint. They all share the following features and issues. Even though you only need a URL to obtain the data, we advise that you read through and understand all of these before you start any significant work.

Cache invalidation: This endpoints refresh at most once every 12 hours


Not (Yet) Guaranteed Current
About 3% of players are still actively using the old "v2" website for some actions. When these players perform an action that modifies the data you are requesting, the data may be out of date when we deliver it to you. We expect to remove the option of using v2 in the coming months. Until then, you can communicate to your users that data accuracy will be improved if they and their opponents are all using the new v3 website.

This issue does not apply to people using the mobile apps.


English
URL responses are the same for everyone, no matter who or where they are. This speeds up delivery, but also means that in cases where the data contain words (for example, reasons for game ending, error responses), these words will be in English.


Rate Limiting
Your serial access rate is unlimited. If you always wait to receive the response to your previous request before making your next request, then you should never encounter rate limiting.

However, if you make requests in parallel (for example, in a threaded application or a webserver handling multiple simultaneous requests), then some requests may be blocked depending on how much work it takes to fulfill your previous request. You should be prepared to accept a "429 Too Many Requests" response from our server for any non-serial request that you make.

In some cases, if we detect abnormal or suspicious activity, we may block your application entirely. If you supply a recognizable user-agent that contains contact information, then if we must block you application we will attempt to contact you to correct the problem.


How to get the PubAPI data
The PubAPI endpoints can be called, by any kind of client or browsers that supports the HTTP protocol.

So if you only want to see what happens when you issue a request to an endpoint you can open your browser and write in the address bar the endpoint you are interested in (for example the Profile endpoint.

The response is compressed, but there are many tools only that can render that response in a more readable format (gor example https://jsonformatter.curiousconcept.com).

If you have access to a Command Prompt/Terminal Window you can use the curl command that will give you more useful information.
For example the command "curl -v https://api.chess.com/pub/player/hikaru" will return, among with the response, a lot of useful data such as the response code, Etag, date, last-modified that are very useful to check if you are retrieving fresh or cached data.
If you want to play with cdata retrieved by curl you can use jq as was shown in these brilliant examples by @pmaugeri.

If you don't want to deal with command line there are many free tools online that provide an easier user interface. The ones that we use mostly in our team are Postman and Insomnia.

If you use Postman or Insomnia, we have released a collection of endpoints that you can download from HERE. After installing the collection you will find all the current endpoints that you can call by a click (and analyze the response, convert the call into a language of your choice etc.) . If you need instructions on how import collections, check this link for Postman or this link for Insomnia.

All time fields are expressed as "timestamp", which is a number calculated as the time measured in the number of seconds since the Unix Epoch (January 1 1970 00:00:00 GMT). All programming languages have functions to convert timestamps to an human-readable format, but if you want to try by hand you can use one of the many online converters.
