
import random

print("=" * 35)
print("   GAMING CREATOR TOOL")
print("=" * 35)

ideas = {
    "Free Fire": [
        "Can I win using only a pistol?",
        "Best clutch moments compilation",
        "My ranked gameplay highlights",
        "1 HP comeback challenge",
        "Top 5 mistakes beginners make"
    ],
    "Roblox": [
        "Funniest moments with friends",
        "Can I win without taking damage?",
        "Best clutch moments",
        "Testing a game for the first time",
        "My funniest gaming fails"
    ],
    "Minecraft": [
        "Survive one night challenge",
        "Build a secret base",
        "Beginner survival tips",
        "Can I find diamonds today?",
        "My best survival moments"
    ]
}

def video_ideas():
    print("\nGames: Free Fire, Roblox, Minecraft")
    game = input("Enter your game: ").strip().title()

    if game in ideas:
        print("\nYour video ideas:")
        for i, idea in enumerate(ideas[game], 1):
            print(f"{i}. {idea}")
    else:
        print("Game not found. Try one from the list.")

def title_creator():
    game = input("\nEnter game name: ").strip()
    topic = input("Enter video topic: ").strip()

    titles = [
        f"Can I Master {topic} in {game}?",
        f"My Best {topic} Moments in {game}",
        f"This {game} Challenge Was Insane!",
        f"{topic} - Gaming Highlights"
    ]

    print("\nTitle ideas:")
    for title in titles:
        print("-", title)

    print("\nDescription:")
    print(f"Watch my {game} gameplay!")
    print(f"Today's video: {topic}")
    print("Like and subscribe for more gaming videos!")

    tags = game.replace("#", "").replace(" ", "")
    print("\nHashtags:")
    print(f"#{tags} #Gaming #GamingShorts")

def view_estimator():
    print("\n--- View Estimate ---")
    try:
        views = int(input("Views on your last 5 videos (comma-separated): "))
        # This line is replaced below to accept all five values.
    except ValueError:
        print("Enter numbers separated by commas.")
        return

def predict_views():
    try:
        data = input(
            "\nEnter views of your last 5 videos, separated by commas: "
        )
        past_views = [int(x.strip()) for x in data.split(",")]

        if len(past_views) != 5 or any(v < 0 for v in past_views):
            print("Enter exactly 5 non-negative view counts.")
            return

        average = sum(past_views) / 5

        print(f"\nAverage views: {average:.0f}")
        print(f"Rough planning estimate: {average * 0.5:.0f} "
              f"to {average * 1.5:.0f} views")
        print("This is only a rough estimate, not an AI prediction.")

    except ValueError:
        print("Please enter valid whole numbers.")

while True:
    print("\nChoose an option:")
    print("1. Generate video ideas")
    print("2. Create titles and hashtags")
    print("3. Estimate future views")
    print("4. Exit")

    choice = input("Your choice: ").strip()

    if choice == "1":
        video_ideas()
    elif choice == "2":
        title_creator()
    elif choice == "3":
        predict_views()
    elif choice == "4":
        print("Keep creating. Good luck!")
        break
    else:
        print("Invalid choice. Select 1, 2, 3 or 4.")
        
