# Event-management-
Major project 
class Event:
    def __init__(self, name, date, location, description):
        self.name = name
        self.date = date
        self.location = location
        self.description = description

class EventManager:
    def __init__(self):
        self.events = []

    def add_event(self, event):
        self.events.append(event)

    def view_events(self):
        if self.events:
            print("List of Events:")
            for idx, event in enumerate(self.events, start=1):
                print(f"{idx}. {event.name} - Date: {event.date} - Location: {event.location}")
        else:
            print("No events found.")

    def delete_event(self, index):
        try:
            del self.events[index]
            print("Event deleted successfully.")
        except IndexError:
            print("Invalid event index.")

def main():
    event_manager = EventManager()

    while True:
        print("\nEvent Management System")
        print("1. Add Event")
        print("2. View Events")
        print("3. Delete Event")
        print("4. Exit")

        choice = input("Enter your choice: ")

        if choice == '1':
            name = input("Enter event name: ")
            date = input("Enter event date: ")
            location = input("Enter event location: ")
            description = input("Enter event description: ")
            event = Event(name, date, location, description)
            event_manager.add_event(event)
            print("Event added successfully.")
        elif choice == '2':
            event_manager.view_events()
        elif choice == '3':
            index = int(input("Enter the index of the event to delete: ")) - 1
            event_manager.delete_event(index)
        elif choice == '4':
            print("Exiting...")
            break
        else:
            print("Invalid choice. Please try again.")

if __name__ == "__main__":
    main()
    
