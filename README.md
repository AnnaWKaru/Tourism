# Tourism
Tourism Service
import java.util.List;

public class TourismService {

    private List<Tourist> tourists;

    // Constructor
    public TourismService(List<Tourist> tourists) {
        this.tourists = tourists;
    }

    // Method to add a tourist
    public void addTourist(Tourist tourist) {
        tourists.add(tourist);
        System.out.println("Tourist added: " + tourist);
    }

    // Method to remove a tourist
    public void removeTourist(Tourist tourist) {
        tourists.remove(tourist);
        System.out.println("Tourist removed: " + tourist);
    }

    // Method to display all tourists
    public void displayAllTourists() {
        System.out.println("All Tourists:");
        for (Tourist tourist : tourists) {
            System.out.println(tourist);
        }
    }

    // Method to find tourist by name
    public Tourist findTouristByName(String name) {
        for (Tourist tourist : tourists) {
            if (tourist.getName().equals(name)) {
                return tourist;
            }
        }
        return null; // Tourist not found
    }

    // Method to update tourist information
    public void updateTourist(Tourist oldTourist, Tourist newTourist) {
        int index = tourists.indexOf(oldTourist);
        if (index != -1) {
            tourists.set(index, newTourist);
            System.out.println("Tourist information updated: " + oldTourist.getName());
        } else {
            System.out.println("Tourist not found.");
        }
    }

    // Inner class representing a Tourist
    public static class Tourist {
        private String name;
        private String nationality;

        // Constructor
        public Tourist(String name, String nationality) {
            this.name = name;
            this.nationality = nationality;
        }

        // Getters and setters
        public String getName() {
            return name;
        }

        public void setName(String name) {
            this.name = name;
        }

        public String getNationality() {
            return nationality;
        }

        public void setNationality(String nationality) {
            this.nationality = nationality;
        }

        // toString method
        @Override
        public String toString() {
            return "Tourist{" +
                    "name='" + name + '\'' +
                    ", nationality='" + nationality + '\'' +
                    '}';
        }
    }
}
