# Scala Testing Exercises

Practice writing Scala and Scala tests with the code below:

1. Complete the Room and Hotel classes where there are ???
2. Write Unit tests for each function you fill in. There should be 4 unit tests.


    case class Guest(name: String)
    
    case class Room(number: Int, guest: Option[Guest] = None){ room =>
    
      def isAvailable(): Boolean = ???
    
      def checkin(guest: Guest): Room = ???
    
      def checkout(): Room = ???
    
    }
    
    /*
     * We will automatically create 10 rooms unless otherwise specified
     */
    case class Hotel(
      rooms: List[Room] = (1 to 10).map(n => Room(number=n)).toList) {
    
      def checkin(personName: String): Hotel = ???
    
    }
    
Advanced:

1. Use Scalacheck to perform property based testing and generate Guests and Hotel rooms    