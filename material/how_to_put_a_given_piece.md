1.answer from quora.com
-----------------------
###[How can one know the best place to put a given piece in Tetris?](https://www.quora.com/How-can-one-know-the-best-place-to-put-a-given-piece-in-Tetris)
Would any algorithm give the answer?

####answer1:

**For a non-AI standpoint:**

Knowing where to place a piece depends on your playstyle. A player playing the new standard tetris with full twists (spins) would have a completely different playstyle than someone who stacks tetrises. For me when I build only tetrises in single player, I look 2-3 pieces ahead and place the current piece where it would complement the next 2-3 pieces. If there is not a perfect place to put a piece, I think about if there is a good place to put a piece and later twist a piece into the right place. If not, then I would put the piece in the place that will leave the least amount of harm/when I can actually spin a piece into it.

For multiplayer, I start with "openings" which I suppose you can easily implement in AI as well since it's playing by the book. Certain openings require you to only pay attention to a few pieces at a time, and you can put pieces elsewhere.

**For AI:**

I recommend looking at [Playing TETRIS using the PageRank Algorithm](http://www.ryanheise.com/tetris/tetris_artificial_intelligence.html). Ryan Heise does a great job outlining what he does to develop a great AI for stacking tetrises. Given the TGM system and 4 look ahead, on average it would go through over a million pieces before messing up the stack. If he used the 7 piece bag system, it would even be more accurate (described below).

TGM System:
Generate 4 pieces. The next piece cannot be any of the 4.

7 piece bag System:
If bag is empty, create a new "bag" with 7 pieces.
While bag isn't empty, take a piece out and select that as the next piece.

For multiplayer:
I am sure that the system will crush any human player in multiplayer as the speed outlined in that page is pretty much 2x the speed of the fastest human player out there playing perfectly. If you want a viable strategy that's different, implementing the mindless ZT stacking would not be too difficult. [ST Stacking Setups](http://tetris.wikia.com/wiki/ST_Stacking_Setups) Using the same pieces on that page, if it's a red or blue piece, put it in the middle, blue on the top of the red one. If it's a T, hold it until you can complete a t-spin. if it's a green piece, put it on the side if you can, else hold it. If it's anything else, stack it in the far right 3 slots. It's sustainable unless you are very unlucky.
####end of answer1

####answer2:
Well first you'd have to come up with some criteria for "best". What's your goal? To have as few blocks as possible on the screen at all times? To have the lowest height of the blocks on the screen at all times? To score the most "points" according to some scoring system? To minimize the probability that you have a situation that feeds you blocks where you have no choice but to top out?
For any of those criteria, yes it would be possible to develop an algorithm that determined the "best" place. But it seems to me that most of tetris isn't about finding the "best" place to place things. Even if you make "mistakes" you can clear them up if you're a good player and just keep clearing forever and ever--so every set of moves that let you do this is pretty much the same.

Now in a lot of Tetris games the goal is to get as many blocks down as fast as possible, or clear as many lines as possible, and there's point bonuses for clearing multiple lines at ones. In this case, the "best" move might be moves that minimize the likelihood of you having to slide a piece under another piece, because if you have to do that you don't get to do a "hard drop" which takes less time. And then best moves also would minimize the number of arrow keys the user would have to press--as well as taking into account probability of topping out and all that.

So if you define what "best" move means, then yes, it is possible to have an algorithm. But it would be complicated.
####end of answer2

####answer3:
It depends on many factors, such as whether the piece can be rotated or slid after it visually appears to contact the piece below it (originally, it couldn't), whether you can store a piece for later use (as many versions allow), and whether you're playing single-player or in one of those verses scenarios where the other guy might send you lines at any moment.
In general, the algorithm would have to be weighted based on such factors as height of the highest part of the piece when placed, how close that is to the top of the screen, whether or not you're enclosing a hole or making a long trench inaccessible, and the rate of speed the pieces are moving.

Also, the optimum goal might vary. Are you going for maximum score, maximum lines, or maximum safety from sudden multi-player attack? (Those last two are kinda similar, but the former requires more risk.)

It would be complex to make a perfect algorithm.
####end of answer3