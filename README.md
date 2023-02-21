# # Trabalhando conexao da ide com banco de dados mysql.

# selecionando todos os usuarios 

select * from usuarios


# Fazendo conexão da idea com o banco mysql

# Crio uma classe de conexão e depois faço a utilização dela no main

package conexao;

import java.sql.Connection;
import java.sql.DriverManager;
import javax.swing.JOptionPane;


public class Conexao {
 public Connection getConexao(){
     try {//tenta estabelecer conexao
         Connection conne = DriverManager.getConnection(
         "jdbc:mysql://localhost:3306/usuarios?serverTimezone=UTC",
         "root",
         "123456");
         return conne;
     } catch (Exception erro) {
         // se der erro exibe msg
         
         JOptionPane.showMessageDialog(null, erro.getMessage() + "erro na conn do bd");
                 
         return null;
     }
 }
