# Collection-Framework-Stack-Class

package verysimplecalculator;
import java.util.Stack;
public class VerySimpleCalculator {
public static int evaluateExpression(String expression) {

Stack<Integer> stack = new Stack<>();
for (char ch : expression.toCharArray()) {
if (Character.isDigit(ch)) {
stack.push(Character.getNumericValue(ch));
} else if (ch == '+') {
int operand2 = stack.pop();
int operand1 = stack.pop();
stack.push(operand1 + operand2);
} else if (ch == '-') {
int operand2 = stack.pop();
int operand1 = stack.pop();
stack.push(operand1 - operand2);
}
}
return stack.pop();
}
public static void main(String[] args) {
String expression = "3 + 4 - 2";
int result = evaluateExpression(expression);
System.out.println("Result of the expression " + expression + ":"+ result);
}
}

Output:

Result of the expression '3 + 4 -2': 5
