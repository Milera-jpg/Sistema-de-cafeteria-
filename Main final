import controller.CafeController;
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        CafeController controller = new CafeController();
        Scanner scanner = new Scanner(System.in);
        int opcao;

        System.out.println("=== SISTEMA DE CAFÉ ===");

        do {
            exibirMenu();
            opcao = scanner.nextInt();
            scanner.nextLine();

            switch (opcao) {
                case 1:
                    cadastrarCliente(controller, scanner);
                    break;
                case 2:
                    mostrarCardapio(controller);
                    break;
                case 3:
                    removerProduto(controller, scanner);
                    break;
                case 4:
                    adicionarProdutoPedido(controller, scanner);
                    break;
                case 5:
                    exibirComanda(controller, scanner);
                    break;
                case 6:
                    processarPagamento(controller, scanner);
                    break;
                case 7:
                    consultarTotalPedido(controller, scanner);
                    break;
                case 8:
                    fecharCafe(controller, scanner);
                    break;
                case 9:
                    mostrarTodosPedidos(controller, scanner);
                    break;
                case 0:
                    fecharCafe(controller, scanner);
                    break;
                default:
                    System.out.println("Opção inválida!");
            }
            System.out.println("\nPressione Enter para continuar...");
            scanner.nextLine();
        } while (opcao != 0);
        scanner.close();
    }

    private static void exibirMenu() {
        System.out.print("\n=== MENU PRINCIPAL ===\n" + "1 - Cadastrar Cliente\n" +
        "2 - Mostrar Cardápio\n" + "3 - Remover pedido\n" + "4 - Adicionar Produto a Comanda\n" +
        "5 - Exibir Comanda do Cliente\n" + "6 - Processar Pagamento\n"+
        "7 - Consultar Total do Pedido\n" + "8- Fechando o café\n" +
        "9 - Mostrar Todos os Pedidos\n" + "0 - Sair\n" + "Escolha uma opção: ");
    }

    private static void cadastrarCliente(CafeController controller, Scanner scanner) {
        System.out.println("\n--- CADASTRAR CLIENTE ---");
        int idComanda = controller.cadastrarCliente(scanner);
        if (idComanda != -1) {
            System.out.println("Use a comanda #" + idComanda + " para adicionar produtos!");
        }
    }

    private static void mostrarCardapio(CafeController controller) {
        System.out.println("\n--- CARDÁPIO ---");
        controller.mostraraCardapio();
    }

    private static void adicionarProdutoPedido(CafeController controller, Scanner scanner) {
        System.out.print("\n--- ADICIONAR PRODUTO AO PEDIDO ---\n" + "ID da comanda: ");
        int idPedido = scanner.nextInt();
        System.out.print("ID do produto: ");
        int idProduto = scanner.nextInt();
        controller.adicionarProdutoPedido(idPedido, idProduto);
    }

    private static void removerProduto(CafeController controller, Scanner scanner) {
        System.out.print("\n--- REMOVER PRODUTO ---\n" + "ID do pedido: ");
        int idPedido = scanner.nextInt();
        scanner.nextLine();
        String nomeProduto = scanner.nextLine();
        controller.removerProduto(idPedido, nomeProduto);
    }

    private static void exibirComanda(CafeController controller, Scanner scanner) {
        System.out.print("\n--- EXIBIR COMANDA ---\n" + "Id da comanda: ");
        int idPedido = scanner.nextInt();
        controller.exibirComanda(idPedido);
    }

    private static void processarPagamento(CafeController controller, Scanner scanner) {
        System.out.print("\n--- PROCESSAR PAGAMENTO ---\n" + "ID do pedido: ");
        int idPedido = scanner.nextInt();
        scanner.nextLine();
        System.out.print("Forma de pagamento (Dinheiro/Cartão/Pix): ");
        String formaPagamento = scanner.nextLine();
        controller.processarPagamento(idPedido, formaPagamento);
    }

    private static void consultarTotalPedido(CafeController controller, Scanner scanner) {
        System.out.print("\n--- CONSULTAR TOTAL DO PEDIDO ---\n" + "ID da comanda: ");
        int idPedido = scanner.nextInt();
        controller.consultarTotalPedido(idPedido);
    }

    private static void fecharCafe(CafeController controller, Scanner scanner) {
        boolean podeFechar = controller.verificarFechar();
        if (!podeFechar) {
            System.out.println("Pressione Enter para voltar ao menu...");
            scanner.nextLine();
            return;
        }
        System.out.println("FECHANDO O CAFÉ");

        controller.gerarRelatorioFinal();
        System.out.println("\nAté amanhã!");
        scanner.close();
        System.exit(0);
    }

    private static void mostrarTodosPedidos(CafeController controller, Scanner scanner) {
        System.out.println("\n--- TODOS OS PEDIDOS ---");
        controller.mostrarTodosPedidos();
    }
}
