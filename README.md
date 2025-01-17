Airport Challenge
=================

Answered with help of this video: https://www.youtube.com/watch?v=Vg0cFVLH_EM

Correctly passed user stories 1 & 2 without the video. Worked with the video to implement user story 5, and understood it.
Had already intended to use an array for capacity, and fill it with planes, in a way similar to the Boris Bikes Weekly
exercise. 
Before starting the video, spent time attempting to implement a weather system. Created the following code within
a Weather Class, giving a 10% chance of stormy weather:
def forecast
  prediction = rand(1..10)
  if prediction == 10
    "stormy"
  else
    "fine"
  end
end

 Had also altered by "land" method in the airport class to return different values, depending on whether the weather
 was "fine" or "stormy", by using an 'if' statement. Spent a significant amount of time trying to get this to work,
 without sucess.

Had attempted to run a test along these lines:
context "preventing take-off in stormy weather" do
it "states the plane can't leave due to storms" do
  expect(subject.take_off).to eq "Can't take off during storms."
  end

Plan: to firstly set the chance of stormy weather to 90% (instead of 10%) and run the test until I got both a pass
and a fail. This is a manual process to check the code fundementally works. Next step was to research and update
the code to test for randomness. Had looked at https://blog.appsignal.com/2018/07/31/generating-random-numbers-in-ruby.html
for helpful information on generating random outputs.

Had also researched the double, stub and spies information via https://relishapp.com/rspec/rspec-mocks/docs. Continued to try and understand it, without success. I find the definition of terms without full explanation or context to be very difficult to integrate into my own code.

Researched testing for randomness - could not find anything that I could make sense of. 

At this point, turned to the video walkthrough to attempt to learn how this works in a way I can follow. 

## Did not finish

Did not finish the challenge - chose to stop after implementing the "Planes can't land when weather is stormy" user story. Would complete the next section by adapting this user story, and applying it to the take_off method. 

For the "over-ride capacity" user story, I would like to set the airport capacity as a variable instead of a fixed number. This should allow me to change the capacity if needed. Alternatively, it may be possible to write a method that simply changes it. Several previous tests would need to be refactored to adapt to this.

I have not used the Travis system, as despite signing up for the website I do not understand what it does, how it works, how to us it, or how to get a badge here. The rubocop process was very useful and helpful. 

Matt Freeman.

Instructions
---------

* Challenge time: rest of the day and weekend, until Monday 9am
* Feel free to use google, your notes, books, etc. but work on your own
* If you refer to the solution of another coach or student, please put a link to that in your README
* If you have a partial solution, **still check in a partial solution**
* You must submit a pull request to this repo with your code by 9am Monday morning

Steps
-------

1. Fork this repo, and clone to your local machine
2. Run the command `gem install bundle` (if you don't have bundle already)
3. When the installation completes, run `bundle`
4. Complete the following task:

Task
-----

We have a request from a client to write the software to control the flow of planes at an airport. The planes can land and take off provided that the weather is sunny. Occasionally it may be stormy, in which case no planes can land or take off.  Here are the user stories that we worked out in collaboration with the client:

```
As an air traffic controller 
So I can get passengers to a destination 
I want to instruct a plane to land at an airport

As an air traffic controller 
So I can get passengers on the way to their destination 
I want to instruct a plane to take off from an airport and confirm that it is no longer in the airport

As an air traffic controller 
To ensure safety 
I want to prevent takeoff when weather is stormy 

As an air traffic controller 
To ensure safety 
I want to prevent landing when weather is stormy 

As an air traffic controller 
To ensure safety 
I want to prevent landing when the airport is full 

As the system designer
So that the software can be used for many different airports
I would like a default airport capacity that can be overridden as appropriate
```

Your task is to test drive the creation of a set of classes/modules to satisfy all the above user stories. You will need to use a random number generator to set the weather (it is normally sunny but on rare occasions it may be stormy). In your tests, you'll need to use a stub to override random weather to ensure consistent test behaviour.

Your code should defend against [edge cases](http://programmers.stackexchange.com/questions/125587/what-are-the-difference-between-an-edge-case-a-corner-case-a-base-case-and-a-b) such as inconsistent states of the system ensuring that planes can only take off from airports they are in; planes that are already flying cannot take off and/or be in an airport; planes that are landed cannot land again and must be in an airport, etc.

For overriding random weather behaviour, please read the documentation to learn how to use test doubles: https://www.relishapp.com/rspec/rspec-mocks/docs . There’s an example of using a test double to test a die that’s relevant to testing random weather in the test.

Please create separate files for every class, module and test suite.

In code review we'll be hoping to see:

* All tests passing
* High [Test coverage](https://github.com/makersacademy/course/blob/master/pills/test_coverage.md) (>95% is good)
* The code is elegant: every class has a clear responsibility, methods are short etc. 

Reviewers will potentially be using this [code review rubric](docs/review.md).  Referring to this rubric in advance will make the challenge somewhat easier.  You should be the judge of how much challenge you want this weekend.

**BONUS**

* Write an RSpec **feature** test that lands and takes off a number of planes

Note that is a practice 'tech test' of the kinds that employers use to screen developer applicants.  More detailed submission requirements/guidelines are in [CONTRIBUTING.md](CONTRIBUTING.md)

Finally, don’t overcomplicate things. This task isn’t as hard as it may seem at first.

* **Submit a pull request early.**  There are various checks that happen automatically when you send a pull request.  **Fix these issues if you can**.  Green is good.

* Finally, please submit a pull request before Monday at 9am with your solution or partial solution.  However much or little amount of code you wrote please please please submit a pull request before Monday at 9am.
