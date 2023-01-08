# kitab-station

#include <graphics.h>
#include <iostream>

int main() {
  int gd = DETECT, gm;
  initgraph(&gd, &gm, "");

  // Draw a square
  rectangle(100, 100, 200, 200);

  while (true) {
    std::cout << "Enter a transformation (s = scale, t = translate, r = rotate, sh = shear, ref = reflect, q = quit): ";
    char transform;
    std::cin >> transform;

    switch (transform) {
      case 's': {
        // Scale the square
        int x, y;
        std::cout << "Enter scaling factor for x-direction: ";
        std::cin >> x;
        std::cout << "Enter scaling factor for y-direction: ";
        std::cin >> y;
        scale(x, y);
        break;
      }
      case 't': {
        // Translate the square
        int x, y;
        std::cout << "Enter translation distance for x-direction: ";
        std::cin >> x;
        std::cout << "Enter translation distance for y-direction: ";
        std::cin >> y;
        translate(x, y);
        break;
      }
      case 'r': {
        // Rotate the square
        int angle;
        std::cout << "Enter angle of rotation: ";
        std::cin >> angle;
        rotate(angle);
        break;
      }
      case 'sh': {
        // Shear the square
        int x, y;
        std::cout << "Enter shearing factor for x-direction: ";
        std::cin >> x;
        std::cout << "Enter shearing factor for y-direction: ";
        std::cin >> y;
        shear(x, y);
        break;
      }
      case 'ref': {
        // Reflect the square
        bool x, y;
        std::cout << "Reflect about x-axis (1 = yes, 0 = no): ";
        std::cin >> x;
        std::cout << "Reflect about y-axis (1 = yes, 0 = no): ";
        std::cin >> y;
        reflect(x, y);
        break;
      }
      case 'q': {
        // Quit the program
        closegraph();
        return 0;
      }
      default: {
        std::cout << "Invalid transformation" << std::endl;
        break;
      }
    }
  }
}
