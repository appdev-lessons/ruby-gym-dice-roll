# Ruby Gym: Dice Roll

Write a program that:
- generates a random guess for a dice roll (a number between 1 and 6)
- generates another random dice roll (a number between 1 and 6).  
- if the guess is right, your program should print: 
    ```
    "You guessed correctly."
    ```

- if the guess is not right, your program should print: 
    ```
    "Sorry, you guessed X. The die landed on Y." 
    ```

    (where `X` is the random guess and `Y` is the roll)

**Hints**: Use the `rand` method for the guess and dice roll like so: `rand(X)`, where `X` is the number of sides for a dice.

```ruby
# write your program below using the provided variables to start
player_guess =
computer_roll =
```
{: .repl #dice_roll title="Dice Roll" readonly_lines="[1]"}


```ruby
describe "Dice Roll" do
  it "prints 'You guessed correctly' when the guess is 3 and the roll is 3" do
    path = "/tmp/code.rb"
    allow_any_instance_of(Object).to receive(:rand).and_return(3)
    expect { require_relative(path) }.to output(/You guessed correctly/).to_stdout
  end
end
```
{: .repl-test #dice_roll_test_1 for="dice_roll" title="Dice Roll prints 'You guessed correctly' when the guess is 3 and the roll is 3" points="1"}

```ruby
describe "Dice Roll" do
  it "prints 'Sorry, you guessed X. The die landed on Y' when the guess is 3 and the roll is 5" do
    path = "/tmp/code.rb"
    allow_any_instance_of(Object).to receive(:rand).and_return(3, 5)
    expect { require_relative(path) }.to output(/Sorry, you guessed 3. The die landed on 5/).to_stdout
  end
end
```
{: .repl-test #dice_roll_test_2 for="dice_roll" title="Dice Roll prints 'Sorry, you guessed X. The die landed on Y' when the guess is 3 and the roll is 5" points="1"}
