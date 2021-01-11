---
published: false
categories:
  - pair-programming
  - notes
  - future
  - ideas
---

While pair programming, especially while using the driver-navigator variation, I like to take notes about:

  * What's on my mind at that moment
  * Future features related to the current one
  * Defects that will be taken care of
  * Other designs
  * TODO items for my personal / professional life
  
  
I think of it as low-level GTD. I really like to focus on the important stuff and later will review the notes. 

After processing the tasks / notes, I will cross the whole page meaning this has been taken care of (even if it's only adding it to a more durable / searchable list)

## Example

### Pair programming notes (with @trikitrok)

12:00

As an example, today's notes from doing [this exercise][tire-pressure] with @trikitrok:

  * Tire pressure exercise
  * Alarm <- add unit tests
  * minimize public API changes
  * seam is the method, "popNext...", when the sensor is injected. With sensor = new ... there's no seam
  * Try to find business concept to test names
  * the commit message is another feedback loop for naming. More productive because code is more read than written [another post about this coming]
  * Maybe the test code doesn't have to be as DRY as production code [don't really agree with this]
    * Change in structure
    * testable
    * clean code
      *  important vs urgent
  * ! [TODO] missing test for two checks one after the other. Especially when alarm = true -> false
  * commit message: prefer explaining why change rather than how it was changed or what it was changed. See commit 4d26
  * If I did this development via TDD, would this be a notification or a dependency?
    * What if I only need this for test purposes? Think about the above. It's a design choice
  * ? [QUESTION] Does a commit correspond to an unit of work? If so, how much work is an unit of work?
  * If you don't have DI, can't have OCP




[tire-pressure]: https://github.com/alvarogarcia7/TirePressureMonitoringSystemExerciseJava
