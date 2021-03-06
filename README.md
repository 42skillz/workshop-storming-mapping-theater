# Example mapping meet Event Storming

*Material for workshop animation*

*Thomas PIERRAIN & Bruno BOUCARD*

## Intro (5 minutes)
- Hi! My name is ... and we are co-organizers of DDDFR and BDD Paris meetups. We are both coding and facilitating/coaching software production and developers for our customers
- We won’t describe our 2 favorite exploration techniques in details, but give you instead, the strict minimum for you to play with us today.
- We will focus more on how we articulate those 2 techniques : Event Storming and Example Mapping
- There are 4 tables. Every table will play a dev team that will have to build for us an MVP of a seat suggestion service dedicated to theater.
- Please find yourself a group.
 

## Our need: (5 minutes)
- We’ve been contacted by the major theater reservation platform in France so that we help them to __improve the seat reservation process for their street corner desks__; the ones we have in Paris and where we can buy tickets to see a play in a theater, usually the d-day, in a last minute discount context. 
- Those desks usually have one people : the broker, that helps people to find the seats they want for a given show (i.e.  a play, a theater, a date / hour)


## Event storming 101 (10 minutes)
- Visualization technique where we put domain events (as orange stickies) on a large wall so that we (the IT people) can spot what really matters for the business and when it does happen
- When it does happen : the wall is a timeline. Every sticky put on your right happened after what you have on the left
- A nice way to spot what is important for the biz and __to spread a mental model across various people__
- Chaotic (on purpose)
- Start with one orange sticky: an domain event is a fact, something that has already happened that matters to the business
- E.g.: __SeatSuggested__, SeatSuggestionFailed
- You can start from the left or from the major outcome events in the right (and move backward). What happened before or after?

## Round 1: Event storming our Theater Ticket Office System (15 minutes)
- Figure out what kind of domain events we should have for our use cases?
- Starting point: ___the customer has already expressed which show he or she want to buy tickets for__, and how many people should be seated
- Orange stickies / domain events only
- Try to see errors as events
- Note for us: we should let figure out by themselves what is important (seat suggestion) and what is out of scope for us (play selection, seat reservation, payment)

```json
  - Ticket sold
  - Reservation confirmed
  - Seats reserved
  - Payment succeded
  - Payment failed
  - Reservation canceled
  - Reservation option timeout
  - Reservation option set
  - Suggestion chosen
  - Auditorium Seating shown
  - Seats Suggestions made
  - (Seats) Suggestion requested
  - Auditorium Seating retrieved
  - Show identified
  - ...
```

## Round 1 wrap up (5 minutes)
- Some of you asking us “why” have realized that ___what really matter to us was the seat suggestion module__. 
- Currently: the customers are taking too much time to chose their seats on the broker’s  screen and we experienced situations where queues in the streets are getting longer and longer, and the broker are not always able to sell all the seats before a play is starting (it generates frustrations and lead to missing business opportunities)
- We had the idea of building a seat suggestion module that will provide them a set of seat suggestions for a given request. Hence, the customers will stop to hesitate too much -> speed up the process foe everyone
- To do so, our seat suggestion algorithm should be able to suggest __the best combination of seats__. 


xxxxxxxxx 40 minutes xxxxxxxxxx

---

## Round 2: identify the business rules we have on the wall (15 minutes)
- Try to identify all the business rules we can have in our seat suggestion system
- Put them as blue stickies
- (Our rules:)

```json
    - we should not suggest seats that are already reserved by another customer
    - offer seats nearer the front
    - offer seats nearer the middle of a row
    - if possible, offer adjacent seats to members of the same party
    - parties of over 6 can be split into groups that sit together, with at least 2 in each group
    - avoid leaving single seats unbooked on a row.
    - as a last resort, offer seats that are not adjacent.
```

## Example mapping 101 (15 minutes)
- When we need to start coding a feature, there are so many implicit things to be explicated, so many misunderstandings between the dev and the business, that asking for a concrete example is the safest way to go.
- Example mapping is an awesome technique to identify business rules and what to do through concrete examples
- No gherkin involved. Straight to the point, very efficient low ceremony technique
- 4 kind of cards displayed as a pyramid : user story, business rules, concrete examples and questions

## Round 3: Example mapping one business rule (15 minutes)
- Do example mapping on 1 business rule or two
- Start from the rule and find out at least :
    - One concrete example (green card) for its happy path
    - One concrete example for its unhappy path
- Be as much as possible explicit
- Tips: No matter if your examples arent compliant with all rules. __Firt aim of an example is understanding__. But, most them migth automated after. For those you should find examples that won't violated any other rule?

## Conclusion (10 minutes)
- Event storming : big picture or process level exploration
- Example mapping : clarification of the business rules and invariants we found in the Event Storming so that everyone (the dev especially) have a clear vision of what to do through concrete examples. I.e.: what will be our next acceptance tests
- The business case we used here is __from Emily Bache code kata: Theater reservation__
- Thank you!
- Question?

xxxxxxxxx 105 minutes xxxxxxxxxx

---

__All rights reserved: 42 skillz © 2018__
