package fr.tse.fise2.info4.lab8;

import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.SQLException;
import java.sql.Statement;

/**
 * FIXME Describe the content of this class
 *
 */
public class DatabaseOperations {
	private Connection conn = null;
	
	public DatabaseOperations(String url, String db, String username, String password) {
		// FIXME
		
		
		  
		   try{
		      //STEP 2: Register JDBC driver
		      Class.forName("com.mysql.jdbc.Driver");

		      //STEP 3: Open a connection
		      System.out.println("Connecting to database...");
		      conn = DriverManager.getConnection(url+db, username, password);
		      System.out.println("Connection réussie!");

		     

		   }catch(SQLException se){
		      //Handle errors for JDBC
		      se.printStackTrace();
		   }catch(Exception e){
		      //Handle errors for Class.forName
		      e.printStackTrace();
		   }
		   System.out.println("Goodbye!");
	}

	// START WITH THE CONSTRUCTOR

	/**
	 * FIXME Describe what this query does
	 * 
	 * @return describe the returned value
	 * @throws SQLException 
	 */
	public int query9() throws SQLException {
		// FIXME
		
		 //STEP 4: Execute a query
	      Statement stmt = null;
	      String query="SELECT REGION_ID,REGION_NAME FROM humanresources.regions";
	      stmt = conn.createStatement();
	      ResultSet rs = stmt.executeQuery(query);
	      System.out.println("Data fetshed");
	      while (rs.next()) 
	      {
	      	int i = rs.getInt(1);
	      	String s=rs.getString(2);
	      //	String s=rs.getString(2);
	       System.out.println("ROW="+i+"Name"+s.toString());
	      }
	      
		return -1;
	}

	/**
	 * FIXME Describe what this query does
	 * 
	 * @return describe the returned value
	 */
	public int query11() {
		// FIXME
		return -1;
	}

	/**
	 * FIXME Describe what this query does
	 * 
	 * @return describe the returned value
	 */
	public int query12() {
		// FIXME
		return -1;
	}

	/**
	 * FIXME complete Javadoc
	 * 
	 * @param tableName
	 * @return
	 */
	public int countRowsInTable(String tableName) {
		return -1;
	}

	/**
	 * FIXME complete Javadoc
	 * 
	 * @param dbName
	 * @return
	 */
	public int countElementsInDB(String dbName) {
		return -1;
	}

	/**
	 * Terminate the connection, if any
	 * @throws SQLException 
	 */
	public void close() throws SQLException {
		// FIXME
		 
		conn.close();

	}

}
