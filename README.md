class ChampionshipHistoryTracker:
    def __init__(self):
        self.cricket_championships = []
        self.basketball_championships = []

    def add_cricket_championship(self, name, year, winner, runner_up):
        self.cricket_championships.append({"Name": name, "Year": year, "Winner": winner, "Runner-up": runner_up})

    def add_basketball_championship(self, name, year, winner, runner_up):
        self.basketball_championships.append({"Name": name, "Year": year, "Winner": winner, "Runner-up": runner_up})

    def view_cricket_championships(self):
        print("Cricket Championships:")
        for championship in self.cricket_championships:
            print(championship)

    def view_basketball_championships(self):
        print("Basketball Championships:")
        for championship in self.basketball_championships:
            print(championship)

    def search_championship(self, keyword):
        print("Search Results:")
        found = False
        for championship in self.cricket_championships + self.basketball_championships:
            if keyword.lower() in championship["Name"].lower():
                print(championship)
                found = True
        if not found:
            print("No championships found matching the keyword.")

# Sample usage
tracker = ChampionshipHistoryTracker()

# Adding cricket championships
tracker.add_cricket_championship("ICC Cricket World Cup", 2019, "England", "New Zealand")
tracker.add_cricket_championship("Indian Premier League", 2020, "Mumbai Indians", "Delhi Capitals")

# Adding basketball championships
tracker.add_basketball_championship("NBA Finals", 2020, "Los Angeles Lakers", "Miami Heat")
tracker.add_basketball_championship("EuroLeague", 2019, "CSKA Moscow", "Anadolu Efes")

# Menu-driven program
while True:
    print("\nMenu:")
    print("1. View Cricket Championships")
    print("2. View Basketball Championships")
    print("3. Search Championship")
    print("4. Exit")

    choice = input("Enter your choice: ")

    if choice == "1":
        tracker.view_cricket_championships()
    elif choice == "2":
        tracker.view_basketball_championships()
    elif choice == "3":
        keyword = input("Enter keyword to search: ")
        tracker.search_championship(keyword)
    elif choice == "4":
        print("Exiting the program. Goodbye!")
        break
    else:
        print("Invalid choice. Please try again.")
