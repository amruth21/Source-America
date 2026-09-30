# Source America Design Challenge: CoinCounter

An iPad app that helps cashiers with developmental disabilities run the register on their own,
built for **Furnace Hills Coffee**, a café that employs people with developmental disabilities,
as part of the Source America Design Challenge.

> "Has the potential to allow people with developmental disabilities all over the world to not
> just calculate and return change but also to be able to interact with customers effectively."
> — Furnace Hills Coffee

<a href="https://www.youtube.com/watch?v=Z97Lo3L42wM" target="_blank"><img src="https://img.youtube.com/vi/Z97Lo3L42wM/0.jpg" alt="Demo video" width="480"></a>

## The problem

Making change is the step that most often keeps someone off the register: subtract the total
from the cash handed over, then turn that amount into the right bills and coins, under time
pressure with a customer waiting.

## What the app does

1. **Calculates change.** The cashier enters the sale total and the cash received. The app
   shows the exact number of each denomination to hand back (twenties, tens, fives, ones,
   quarters, dimes, nickels, pennies) as a simple per-denomination count, so there's nothing
   to work out in your head.
2. **Checks the change with the camera.** The design uses the iPad camera and an on-device
   Core ML model to recognize the coins being handed over, so the app can confirm the right
   change before it goes to the customer.

## What's in this repo

| Path | What |
|---|---|
| `CSCoinCounter/` | The main app: change calculator (greedy breakdown into US bills/coins) and a live camera view (AVFoundation + Vision) for coin detection |
| `CoinCounter/` | Earlier prototype of the calculator |
| `CoinClassifier.mlproj/` | Create ML image classifier for coins (quarter heads/tails) |
| `Training Data/`, `Testing Data/` | Images used to train and evaluate the classifier |

The camera screen and classifier are early-stage: the capture pipeline and a trained model are
here, but they aren't wired together in this code.

## Run it

Open `CSCoinCounter/CSCoinCounter.xcodeproj` in Xcode and run on an iPad (or the simulator for
the calculator; the camera needs a device).

**Stack:** Swift · UIKit · AVFoundation · Vision · Core ML / Create ML

Follow the team on Twitter: [@CloudSystems4](https://twitter.com/CloudSystems4)
