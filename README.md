# Base class
class Superhero:
    def __init__(self, name, power, universe):
        self.name = name
        self.power = power
        self.universe = universe
        self.__secret_identity = "Unknown"  # Encapsulated (private attribute)

    def set_secret_identity(self, identity):
        self.__secret_identity = identity

    def get_secret_identity(self):
        return self.__secret_identity

    def describe(self):
        return f"{self.name} from {self.universe} has the power of {self.power}!"

# Subclass inheriting from Superhero
class FlyingHero(Superhero):
    def __init__(self, name, power, universe, max_altitude):
        super().__init__(name, power, universe)
        self.max_altitude = max_altitude

    # Polymorphism: Overriding describe()
    def describe(self):
        return f"{self.name} can fly up to {self.max_altitude} meters!"

# Another subclass
class Speedster(Superhero):
    def __init__(self, name, power, universe, top_speed):
        super().__init__(name, power, universe)
        self.top_speed = top_speed

    def describe(self):
        return f"{self.name} runs at {self.top_speed} km/h!"

# Create instances
hero1 = FlyingHero("SkyBlade", "Flight", "Marvel", 10000)
hero2 = Speedster("Blaze", "Super Speed", "DC", 1200)

# Use the methods
print(hero1.describe())
print(hero2.describe())

# Access encapsulated data via methods
hero1.set_secret_identity("Ava Storm")
print(f"{hero1.name}'s secret identity is {hero1.get_secret_identity()}")
