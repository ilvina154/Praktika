import java.util.*;

class Main {

  public static void main(String[] args) {
    Institution institution = new Institution("Институт", "г. город");
    
    institution.addCourse(new Course("Биология"));
    institution.addCourse(new Course("Инженерная графика"));
    institution.addCourse(new Course("программирование"));

    institution.addLecturer(new Lecturer("Биолог Денисова"));
    institution.addLecturer(new Lecturer("Инженер Лютова "));
    institution.addLecturer(new Lecturer("Программист Паршин "));

    institution.addStudent(new Student("Макеев Андрей Александрович"));
    institution.addStudent(new Student("Кошкин Максим Андреевич"));
    institution.addStudent(new Student("Киреев Петер Алексеевич"));


    Student s = institution.getStudent(1);
    System.out.println();
    System.out.println(s.getName() + " изучает предметы:");
    s.getCourses().forEach(c -> System.out.println(c.getName()));

    System.out.println("\nпредмет " + institution.getCourse(1).getName() + " изучают:\n");
    institution.getCourse(1).getStudents().forEach(st -> System.out.println(st.getName()));
    
    System.out.println("\nпредмет " + institution.getCourse(3).getName() + " ведёт:");
    System.out.println(institution.getCourse(3).getLecturer().getName());
  }

}
