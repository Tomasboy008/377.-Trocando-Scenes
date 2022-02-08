# 377.-Trocando-Scenes
Troca de telas via click em botao
INICIO
_________________________________
package basico;

import javafx.application.Application;
import javafx.geometry.Pos;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.HBox;
import javafx.stage.Stage;

public class Wizard extends Application {
	private Stage janela;
	private Scene passo1;
	private Scene passo2;
	private Scene passo3;
	@Override
	public void start(Stage primaryStage) throws Exception {
		janela = primaryStage;
		criarPasso1();
		criarPasso2();	
		criarPasso3();
		janela.setScene(passo1);
		janela.setTitle("Wizard");
		janela.show();
	}	
	private void criarPasso1() {
		Button proximoPasso = new Button ("Ir p; Passo 2 >>");
		proximoPasso.setOnAction(e -> {
			janela.setScene(passo2);
		});	
		HBox box = new HBox();
		box.setAlignment(Pos.CENTER);
		box.getChildren().add(proximoPasso);
		box.getStyleClass().add("verde");	
		passo1 = new Scene(box, 400, 400);		
	}
	private void criarPasso2() {
		Button passoAnterior = new Button ("<< Voltar p/ Passo 1");
		passoAnterior.setOnAction(e -> {
			janela.setScene(passo1);
		});
		Button proximoPasso = new Button ("Ir p; Passo 3 >>");
		proximoPasso.setOnAction(e -> {
			janela.setScene(passo3);
		});	
		HBox box = new HBox();
		box.setAlignment(Pos.CENTER);
		box.getChildren().add(passoAnterior);
		box.getChildren().add(proximoPasso);
		box.getStyleClass().add("verde");		
		passo2 = new Scene(box, 400, 400);		
	}
	private void criarPasso3() {
		Button passoAnterior = new Button ("<< Voltar p/ Passo 2");
		passoAnterior.setOnAction(e -> {
			janela.setScene(passo2);
		});
		Button proximoPasso = new Button ("Finalizar");
		proximoPasso.setOnAction(e -> {
			System.exit(0);
		});		
		HBox box = new HBox();
		box.setAlignment(Pos.CENTER);
		box.getChildren().add(passoAnterior);
		box.getChildren().add(proximoPasso);
		box.getStyleClass().add("verde");
		passo3 = new Scene(box, 400, 400);
	}
}
