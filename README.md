# ControlledAnimationTimer
Subclass of JavaFX's AnimationTimer that provides control over the Timer's duration. It allows the programmer to specify a maximmum number of steps that the timer will execute. The programmer can also specify Runnable tasks to run before, during, and after the timer's execution.

<h2> Example Usage </h2>

```
// Create timer that will run for 100 steps.
ControlledAnimationTimer timer = new ControlledAnimationTimer(100);
```
```
// Print a mesage right when the timer is started.
timer.addOnStartTask(() -> System.out.println("Start!"));
```
```
// Print a mesage right when the timer ends.
timer.addOnFinishTask(() -> System.out.println("Finished!"));
```
```
// Print a mesage each time the timer ticks.
timer.addOnStepTask(() -> System.out.println("Tick!"));
```
```
// Bind the timer's progress to a text object for display.
IntegerProperty cs = timer.CurrStepProperty();
IntegerProperty ms = timer.MaxStepsProperty();
text.textProperty().bind(Bindings.concat(cs, "/", ms));
```

