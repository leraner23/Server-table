# Server-table
How to make table in the server using springTool / Visual Studio Codes 



Note : you need Docker Desktop ,  Pgadmin , Springtool / Vs Code 

// to create table 

    import java.sql.Connection;
    import java.sql.DriverManager;
    import java.sql.Statement;
     public class create1 {

	public static void main(String[] args) {
		String url = "jdbc:postgresql://localhost:5432/mydatabase";
		String user="postgres";
		String password="*******";
		try(Connection c = DriverManager.getConnection(url,user,password);
				Statement s = c.createStatement()){
			
			String create = """
				CREATE TABLE name(
						id serial primary key,
						name varchar(20) not null,
						address varchar(20) not null,
						age int
						)
						
					""";
					s.execute(create);
			System.out.println("table created");
		}
		catch(Exception e) {
			System.out.println(e + "execption");
		}

	}

    }


// to insert data in the table 

    import java.sql.*;
     public class insert1 {

	public static void main(String[] args) {
		String url = "jdbc:postgresql://localhost:5432/mydatabase";
		String user="postgres";
		String password="*******";
		
		try(Connection c = DriverManager.getConnection(url,user,password);
				Statement s = c.createStatement()){
			String i = "INSERT INTO name(id,name,address,age) VALUES(1,'sujan','kalikanagar',20)";
			String j = "INSERT INTO name(id,name,address,age) VALUES(2,'sudhan','nayamil',20)";
			int ac = s.executeUpdate(i);
			int bc = s.executeUpdate(j);
			System.out.println("number of row inseted"+1);
			System.out.println("number of row inseted"+2);
			
		}
		catch(Exception e) {
			System.out.println(e + "execption");
		}

	}

    }


// to read the data from the database 

     import java.sql.*;
    public class read1 {

	public static void main(String[] args) {
		String url = "jdbc:postgresql://localhost:5432/mydatabase";
		String user="postgres";
		String password="*******";
		try(Connection c = DriverManager.getConnection(url,user,password);
				Statement s = c.createStatement()){
		String select1 = "SELECT * FROM name";
		ResultSet rs = s.executeQuery(select1);
		while(rs.next()){
			int id = rs.getInt("id");
			String name = rs.getString("name");
			String address = rs.getString("address");
			int age = rs.getInt("age");
			
			System.out.println(id);
			System.out.println(name);
			System.out.println(address);
			System.out.println(age);
			System.out.println();
			
		}
		}
		catch(Exception e) {
			System.out.println(e + "execption");
		}

	}
 	}

// to update the data in the database 

    import java.sql.*;
    public class update1 {

	public static void main(String[] args) {
		String url = "jdbc:postgresql://localhost:5432/mydatabase";
		String user="postgres";
		String password="*******";
		try(Connection c = DriverManager.getConnection(url,user,password);
				Statement s = c.createStatement()){
			String Update11 = "UPDATE name SET name = 'sujan+' WHERE age = 20 ";
			int up = s.executeUpdate(Update11);
			System.out.println("data is updated");
		}
		catch(Exception e) {
			System.out.println(e + "execption");
		}

	}
	}



// to delete the data in the database 

    import java.sql.*;
    public class delete1 {

	public static void main(String[] args) {
		String url = "jdbc:postgresql://localhost:5432/mydatabase";
		String user="postgres";
		String password="*******";
		try(Connection c = DriverManager.getConnection(url,user,password);
				Statement s = c.createStatement()){
			String delete11 = "DELETE FROM name WHERE address = 'nayamil'";
			int i = s.executeUpdate(delete11);
			System.out.println("data is deleted");
			
		}
		catch(Exception e) {
			System.out.println(e + "execption");
		}

	}
		
	}




Output: =======>


![Screenshot 2024-04-11 214301](https://github.com/leraner23/Server-table/assets/160107123/f35d7c8a-7e51-4f26-bbf3-4ac62af34cb2)



  



