# Formal languages practicum
# Bringing in
Реализовать алгоритм Эрли, который принимает грамматику и произвольное слово, и отвечает принадлжит ли данное слово языку задаваемому полученной грамматикой или нет.
# Operations
Всего в алгоритме Эрли поддерживаются три операции: Scan, Predict, Complete. Проще говоря, Scan отвечает за «прочтение» нового символа слова, то есть появляются ситуации, которые соответствуют тому, как префикс слова мог быть выведен, Predict отвечает за генерацию возможных ситуаций при прочтении следующего символа, который является нетерминальным, то есть как бы «предсказывает», по каким правилам слово может быть выведено дальше, Complete отвечает как бы за проверку того, было ли правильным «предсказание» со стороны операции Predict.
# language
C++, googletest

# How to run
*    git clone <github link>
*    cd algo Early
*    ./build.sh 
*    cd bin
*    ./Test
*    cd bin     
*    ./mipt_flat_practice2

