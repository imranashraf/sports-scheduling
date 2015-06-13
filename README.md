Sports Scheduling
==========

A C++ library for efficiently generating sports schedules.

Input:
 * Number of divisions (currently limited to 2, see below for future extensions)
 * Number of teams per division (currently all divisions must be of equal size, see below for future extensions)
 * Number of games versus teams in the same division
 * Number of games versus teams in a different division

Output: A home / away schedule satisfying the inputted conditions with the following properties:
 * Games are split into days with no team playing more than 1 game per day; teams without games have a bye.
 * The schedule is made up over the fewest number of days possible to satisfy the inputted conditions (in other words, the minimum number of byes are used).
 * Each team plays the same number of home and away games, unless the total number of games each team plays is odd; in that case, the number of home and away games are one off.
 * Each pair of teams play the same number of games against each other at one team's home as they do at the other team's home, unless the total number of games between the two teams is odd; in that case, these two numbers are one off.
 * Matches are ordered randomly across the days, with the ability to specify a random number generator seed.
 * Team 1's game is the first game in the list of games each day.

How Do I Use the Library to Generate a Schedule?
------------------------------------------------

Compile the library by running `make` in the project's main directory. The library comes with a program called `test` that demonstrates how to use the library.  The program will generate a schedule, print it out to `stdout` and print some statistics for the schedule to `stderr`.  Run `test` with no arguments to display the command line arguments expected by `test`.

This has been tested to work on both Linux with gcc version 4.8.2 and on Windows with mingw.

How Do I Include the Library in My Own Project?
-----------------------------------------------

You should be able to simply copy `src/schedule.hpp` and `src/schedule.cpp` into your project and include them as you would with any other source files.

Future Extensions
-----------------

* Allow for 3 or more divisions.
* Allow for divisions to be separated into conferences / leagues.  With this extension, number of games versus teams in a different division would be split into two new inputs: the number of games versus teams in the same conference but different division, and the number of games versus teams in a different conference.
* Allow for divisions to have different numbers of teams, and specify the number of games played versus each team separately for each division.
* Rather than specify the number of games versus teams in the same (different) division, allow for specifying total number of games versus division (non-division) opponents. With this extension, we would ensure that for each divisional (non-divisional) opponent, the number of games played against that opponent is at most one-off from the number of games played against every other divisional (non-divisional) opponent.
* Allow for matches to be ordered in a more structured manner so that, for example, after any given day, each divisional opponent has been played at most once more than every other divisional opponent.

Feel free to contact me if you would like to see one of these extensions or any other extension implemented sooner rather than later / never.  If you would like to implement one of these extensions yourself, I'm happy to take any pull requests for any solution that is workable and accurate.

Contact
-------

 * Email: [richard.g.gibson@gmail.com](mailto:richard.g.gibson@gmail.com)
 * Twitter: [@RichardGGibson](https://twitter.com/richardggibson)
