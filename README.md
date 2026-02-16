# Monkey-Banana-Problem
class MonkeyBanana:
    def __init__(self):
        self.monkey_position = "door"
        self.box_position = "window"
        self.monkey_on_box = False
        self.has_banana = False

    def walk(self, position):
        if not self.monkey_on_box:
            print(f"Monkey walks from {self.monkey_position} to {position}")
            self.monkey_position = position
        else:
            print("Monkey can't walk while on the box.")

    def push_box(self, position):
        if self.monkey_position == self.box_position and not self.monkey_on_box:
            print(f"Monkey pushes box from {self.box_position} to {position}")
            self.box_position = position
            self.monkey_position = position
        else:
            print("Monkey can't push the box.")

    def climb_box(self):
        if self.monkey_position == self.box_position:
            print("Monkey climbs the box.")
            self.monkey_on_box = True
        else:
            print("Box is not here to climb.")

    def grasp_banana(self):
        if self.monkey_on_box and self.box_position == "center":
            print("Monkey grasps the banana!")
            self.has_banana = True
        else:
            print("Monkey can't reach the banana.")

    def show_state(self):
        print("\nCurrent State:")
        print("Monkey Position:", self.monkey_position)
        print("Box Position:", self.box_position)
        print("Monkey on Box:", self.monkey_on_box)
        print("Has Banana:", self.has_banana)
        print("---------------------------")


# Main Program
game = MonkeyBanana()

game.show_state()

# Step-by-step solution
game.walk("window")
game.push_box("center")
game.climb_box()
game.grasp_banana()

game.show_state()
