import javax.swing.JOptionPane;

public class trabalho {
	static final int REGISTRO = 2;
	
	public static String codigo[] = new  String[REGISTRO];
	public static String nome[] = new String[REGISTRO];
	public static String email[] = new String[REGISTRO];
	public static String cidade[] = new String [REGISTRO];
	public static String uf[] = new String [REGISTRO];
    static int cont=0;
	public static void main(String[] args) {
		String opcao = "";
		JOptionPane entrada = new JOptionPane();
		opcao();
		
	}
	public static void opcao() {
		JOptionPane entrada = new JOptionPane();
		String opcao;
		do  {
			opcao = entrada.showInputDialog("Menu de opcoes\n\n"+
										"1-cadastrar\n"+
					                     "2-consultar\n");
		  
		switch (Integer.parseInt(opcao)) {
			case 1: cadastrar();
			break;
			case 2: consultar();
			break;
		}
	
	 }while (!opcao.equals("6"));
	}
	
	public static void cadastrar() {
		JOptionPane entrada = new JOptionPane();
		for(int cont=0;cont<REGISTRO;cont++) {
			if(cont<REGISTRO) {
			codigo[cont] = entrada.showInputDialog("Digite o codigo");
			nome[cont] = entrada.showInputDialog("Digite o nome");
			email[cont] = entrada.showInputDialog("Digite seu email");
			cidade[cont] = entrada.showInputDialog("Digite a cidade");
			uf[cont] = entrada.showInputDialog("Digite UF");
			}else {
				opcao();
			}
		}
	}
	public static void consultar() {
		String consultCode;
		JOptionPane entrada = new JOptionPane();
		consultCode = entrada.showInputDialog("Digite o codigo para consulta");
		for(int cont=0;cont<REGISTRO;cont++) {
			if (consultCode.equals(codigo[cont])){
				JOptionPane.showMessageDialog(null,nome[cont]+"\n"+email[cont]);
			}
			
		}
	}

}
