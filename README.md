// SPDX-License-Identifier: MIT
pragma solidity ^0.8.25;

contract DailyExerciseTracking {

    function Morning(uint MorningConsumpt) public pure {
        require(MorningConsumpt > 100, "I'm still hungry, I need more food in my breakfast.");
    }

    function Lunch(uint LunchConsumpt) public pure {
        if (LunchConsumpt < 50) {
            revert("I'm still hungry, I need food in my lunch.");
        }
    }

    function Dinner(uint256 DinnerConsumpt) public pure {
        assert(DinnerConsumpt == 20);
    }

    function Exercise(uint ExerciseDuration) public pure {
        require(ExerciseDuration >= 30, "You need to exercise for at least 30 minutes daily.");
    }
