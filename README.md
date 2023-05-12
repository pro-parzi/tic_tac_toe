# tic_tac_toe

Теория
Мой проект "Крестики-нолики" - это игра, в которой пользователь играет против алгоритма. Игра реализована в консоли и запускается на replit. 
Консольная игра "Крестики-нолики" обычно реализуется с помощью функций и структур данных, которые моделируют игровое поле, игроков и правила игры. Одна из важных функций в такой реализации - это функция, которая отвечает за определение  хода компьютера. Вот отрывок кода с комментариями, с помощью которого компьютер выставляет символ 'O' на игровое поле.

void computerMove(char board[], char computerSymbol, char playerSymbol) {
    // Проходим по всем ячейкам доски и пытаемся поставить символ компьютера в каждую свободную ячейку
    for (int i = 0; i < 9; i++) {
        if (board[i] == ' ') {
            board[i] = computerSymbol;
            // Если компьютер может выиграть на следующем ходу, то ставим символ компьютера в эту ячейку и выходим из функции
            if (isWinner(board, computerSymbol)) {
                return;
            }
                // Иначе, если игрок может выиграть на следующем х оду, то ставим символ игрока в эту ячейку, чтобы предотвратить его победу, и выходим из функции
            else if (isWinner(board, playerSymbol)) {
                board[i] = playerSymbol;
                return;
            }
            else {
                board[i] = ' ';
            }
        }
    }
    do {
        int move = rand() % 9;
        if (board[move] == ' ') {
            board[move] = computerSymbol;
            break;
        }
    } while (true);
}

Перед началом игры с вероятностью 50 % с помощью этого отрывка кода (\033[1;34m \033[0m это команда, которая окрашивает текст в консоли в определенный цвет):

if (rand() % 2 == 0) {    //Кто будет ходить первым
    cout << "\033[1;34mComputer start the first.\033[0m" << endl;
    computerMove(board, computerSymbol, playerSymbol);
}
else {
    cout << "\033[1;34mYou start the first.\033[0m" << endl;
}

Также одной из самых важных функций для работы программы это функция для созжания игрового поля:

void drawBoard(char board[]) {
    cout << " " << board[0] << " \033[1;36m┃\033[0m " << board[1] << " \033[1;36m┃\033[0m " << board[2] << endl;
    cout << "\033[1;36m━━━╋━━━╋━━━\033[0m" << endl;
    cout << " " << board[3] << " \033[1;36m┃\033[0m " << board[4] << " \033[1;36m┃\033[0m " << board[5] << endl;
    cout << "\033[1;36m━━━╋━━━╋━━━\033[0m" << endl;
    cout << " " << board[6] << " \033[1;36m┃\033[0m " << board[7] << " \033[1;36m┃\033[0m " << board[8] << endl;
}

Видно, что я обращаюсь к каждому сектору игрового поля как к элементу массива от 0 до 8, также реализируется и ход игрока или алгоритма, чтобы юзеру было легко играть я сделал таблицу, с помощью которой игрок видит, за какой сектор игрового поля отвечает индекс элемента массива. 
![image](https://github.com/pro-parzi/tic_tac_toe/assets/128066686/c4fae0a8-095b-4509-a381-f0762732958a)




