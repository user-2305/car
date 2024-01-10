# car

Для нарисования машинки, похожей на ту, что на картинке, мы будем использовать классы JFrame и JPanel. Класс JFrame используется для создания окна приложения, а JPanel - для рисования графики.

Вот пример кода для нарисования машинки:
```java
import javax.swing.*;
import java.awt.*;
import java.awt.geom.*;

public class Car extends JPanel {
    private int x, y;

    public Car() {
        x = 50;
        y = 50;
    }

    public void paintComponent(Graphics g) {
        super.paintComponent(g);
        drawCar(g);
    }

    private void drawCar(Graphics2D g2d) {
        g2d.setColor(Color.BLACK);
        g2d.fillRect(x, y, 100, 50); // Body

        g2d.setColor(Color.RED);
        g2d.fillOval(x + 40, y + 20, 20, 10); // Left headlight
        g2d.fillOval(x + 60, y + 20, 20, 10); // Right headlight

        g2d.setColor(Color.BLACK);
        g2d.fillOval(x + 70, y + 35, 10, 10); // Left wheel
        g2d.fillOval(x + 85, y + 35, 10, 10); // Right wheel

        g2d.setColor(Color.BLACK);
        g2d.fillOval(x + 30, y + 35, 10, 10); // Left wheel (rear)
        g2d.fillOval(x + 50, y + 35, 10, 10); // Right wheel (rear)

        g2d.setColor(Color.BLACK);
        g2d.drawLine(x + 20, y + 15, x + 60, y + 15); // Hood line
    }

    public static void main(String[] args) {
        SwingUtilities.invokeLater(new Runnable() {
            @Override
            public void run() {
                JFrame frame = new JFrame("Car");
                frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
                frame.setContentPane(new Car());
                frame.setSize(200, 100);
                frame.setLocationRelativeTo(null);
                frame.setVisible(true);
            }
        });
    }
}
```
В этом примере мы создаем класс Car, наследующийся от JPanel. В методе paintComponent мы рисуем машину в виде прямоугольника с круглыми фары и колесами.

Когда этот код будет запущен, окно с машинкой будет отображено на экране.
