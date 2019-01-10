# Elevens 7

Follow the instructions provided for Activity 7 in the student lab guide. This is more of an exploratory lab, so you will not need to copy any of your previous code into the repo. Answer the questions from the Student Guide in this document and ensure that you save and push the repo. You have one week to complete this lab.

1. What items would be necessary if you were playing a game of Elevens at your desk (not on the computer)? List the private instance variables needed for the `ElevensBoard` class.

    * Answer: A standard deck of cards with numbers and suits, a person to play the game
    BOARD_SIZE, RANKS, SUITS, POINT_VALUES, Deck


2. Write an algorithm that describes the actions necessary to play the Elevens game.

    * Answer: Use nine cards, if two cards add up to eleven, you remove those two cards and replace them from the deck. If you have a jack, queen, and king, you can remove all of them. Otherwise, you cannot.

3. Now examine the partially implemented `ElevensBoard.java` file found in this repository. Does the `ElevensBoard` class contain all the state and behavior necessary to play the game?

    * Answer: It has all of the necessary methods to complete the game.

4. `ElevensBoard.java` contains three helper methods. These helper methods are private because they are only called from the ElevensBoard class.

  * a. Where is the `dealMyCards` method called in ElevensBoard?

      * Answer: ElevensBoard and newGame

  * b. Which `public` methods should call the `containsPairSum11` and `containsJQK` methods?

      * Answer: replaceSelectedCards, isLegal, anotherPlayIsPossible

  * c. It’s important to understand how the `cardIndexes` method works, and how the list that it returns is used. Suppose that `cards` contains the elements shown below. Trace the execution of the `cardIndexes` method to determine what list will be returned. Complete the diagram below by filling in the elements of the returned list, and by showing how those values index `cards`. Note that the returned list may have less than 9 elements.

    * `cards`

| 0  | 1  |  2   | 3  |  4   |  5   | 6  | 7  |  8   |
|:--:|:--:|:----:|:--:|:----:|:----:|:--:|:--:|:----:|
| J♥ | 6♣ |`null`| 2♠ |`null`|`null`| A♠ | 4♥ |`null`|

   *  * Answer

| 0  | 1  | 2  | 3  | 4  | 5  | 6  | 7  | 8  |
|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|
| J♥ | 6♣ | 2♠ | A♠ | 4♥ |    |    |    |    |

  * d. Complete the following `printCards` method to print all of the elements of cards that are indexed by `cIndexes`.
```java
public static printCards(ElevensBoard board) {
    List<Integer> cIndexes = board.cardIndexes();
    /* Your code goes here. */
}
```

  *  * Answer:
  for (int i = 0; i < cIndexes.size; i++){
    System.out.print(cIndexes.get(i));
  }

  * e. Which one of the methods that you identified in question 4b above needs to call the `cardIndexes` method before calling the `containsPairSum11` and `containsJQK` methods? Why?

      * Answer:
      replaceSelectedCards
