# EX 7 : THREE DIMENSIONAL TRANSFORMATIONS

## AIM :
 
 To implement the various transformations on three dimensional odjects using a c coding.

## EQUIPMENT REQUIRED:

●	Hardware: Personal Computer (PC)

●	Software: C Compiler

## ALGORITHM :


   Step 1 : Start.

   Step 2 : Draw an image with default parameters.

   Step 3 : Get the choice from user.

   Step 4 : Get the parameters for transformation.

   Step 5 : Perform the transformation.

   Step 6 : Display the output.

   Step 7 : Stop.

## Program :
```
#include <stdio.h>
#include <conio.h>
#include <graphics.h>
#include <math.h>

int maxx, maxy, midx, midy;

void drawAxis() {
    line(midx, 0, midx, maxy);   // Y-axis
    line(0, midy, maxx, midy);   // X-axis
}

int main() {
    int gd = DETECT, gm;
    float x, y, z;
    float angle;
    float x1, y1, x2, y2;

    initgraph(&gd, &gm, "c:\\turboc3\\bgi");

    maxx = getmaxx();
    maxy = getmaxy();
    midx = maxx / 2;
    midy = maxy / 2;

    cleardevice();
    drawAxis();

    // Original bar
    bar3d(midx + 50, midy - 100, midx + 60, midy - 90, 5, 1);
    printf("Original Object drawn at (50, -100)\n");

    // TRANSLATION
    printf("\nEnter Translation Factors (tx ty tz): ");
    scanf("%f %f %f", &x, &y, &z);

    cleardevice();
    drawAxis();
    printf("After Translation\n");
    bar3d(midx + (50 + x), midy - (100 + y), midx + (60 + x), midy - (90 + y), 5 + z, 1);

    // SCALING
    printf("\nEnter Scaling Factors (sx sy sz): ");
    scanf("%f %f %f", &x, &y, &z);

    cleardevice();
    drawAxis();
    printf("After Scaling\n");
    bar3d(midx + (x * 50), midy - (y * 100), midx + (x * 60), midy - (y * 90), 5 * z, 1);

    // ROTATION
    printf("\nEnter Rotating Angle (in degrees): ");
    scanf("%f", &angle);
    angle = angle * (3.14159 / 180); // convert to radians

    // Rotation about Z-axis (2D rotation)
    x1 = 50 * cos(angle) - 100 * sin(angle);
    y1 = 50 * sin(angle) + 100 * cos(angle);
    x2 = 60 * cos(angle) - 90 * sin(angle);
    y2 = 60 * sin(angle) + 90 * cos(angle);

    cleardevice();
    drawAxis();
    printf("After Rotation about Z-axis\n");
    bar3d(midx + x1, midy - y1, midx + x2, midy - y2, 5, 1);

    getch();
    closegraph();
    return 0;
}
```
## Output :
<img width="634" height="475" alt="image" src="https://github.com/user-attachments/assets/7110ebda-ad2d-4aa6-af2f-7c0642899e94" />

<img width="637" height="507" alt="image" src="https://github.com/user-attachments/assets/daba65b2-2741-4b08-9d23-ef15ac2b982b" />


## Result :
### Thus the Three Dimensional Transformation Exceuted successfully.
