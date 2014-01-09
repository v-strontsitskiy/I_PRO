#include "stdafx.h"
#include <gl\glut.h>
#include <math.h>


float WinWid=1000.0;
float WinHei=400.0;
int q=0;
int z=0;



void Draw()
{
glClear(GL_COLOR_BUFFER_BIT);
glColor3f(1.0,1.0,1.0);
glBegin(GL_LINE_LOOP); 

 for(int i = 0; i < 30; i++) //колесол
 { 
  float angle = 2.0 * 3.1415926 * float(i) / 30; 

  float dx = 10 * cosf(angle);
  float dy = 10 * sinf(angle);

  glVertex2f(130 + dx+q, 30 + dy);
}

 glEnd(); 
 glBegin(GL_LINE_LOOP); 

 for(int i = 0; i < 30; i++) //колесоп
 { 
  float angle = 2.0 * 3.1415926 * float(i) / 30; 

  float dx = 10 * cosf(angle);
  float dy = 10 * sinf(angle);

  glVertex2f(180 + dx+q, 30 + dy);
} glEnd();

  glBegin(GL_LINE_LOOP); //машинка
  glVertex2f(140+q,30);
   glVertex2f(170+q,30);
    glEnd(); 
glBegin(GL_LINE_LOOP);
glVertex2f(210+q,30);
   glVertex2f(190+q,30);
glEnd(); 
glBegin(GL_LINE_LOOP);
glVertex2f(210+q,30);
glVertex2f(210+q,45);
  glEnd(); 
glBegin(GL_LINE_LOOP);
glVertex2f(210+q,45);
glVertex2f(100+q,45); 
 glEnd(); 
 glBegin(GL_LINE_LOOP);
glVertex2f(100+q,45);
   glVertex2f(100+q,30);
glEnd(); 
glBegin(GL_LINE_LOOP);
glVertex2f(100+q,30);
   glVertex2f(120+q,30);
glEnd(); 
glBegin(GL_LINE_LOOP);
glVertex2f(155+q,65);
   glVertex2f(155+q,45);
glEnd(); 
glBegin(GL_LINE_LOOP);
glVertex2f(155+q,65);
   glVertex2f(190+q,65);
glEnd();
glBegin(GL_LINE_LOOP);
glVertex2f(190+q,65);
   glVertex2f(190+q,45);
glEnd();

glBegin(GL_LINE_LOOP); //качеля

 for(int i = 0; i < 30; i++) 
 { 
  float angle = 2.0 * 3.1415926 * float(i) / 30; 

  float dx = 12 * cosf(angle);
  float dy = 12 * sinf(angle);

  glVertex2f(500 + dx, 35 + dy);
} glEnd();
 glBegin(GL_LINES); 
  glVertex2f(360,50-z*0.5);
  glVertex2f(640,50+z*0.5);
  glVertex2f(640,50+z*0.5);
  glVertex2f( 640,46+z*0.5);
  glVertex2f( 640,46+z*0.5);
  glVertex2f(360,46-z*0.5);
  glVertex2f(360,46-z*0.5);
  glVertex2f(360,50-z*0.5); 
  glEnd();

glBegin(GL_LINES);  //земля
  glVertex2f(10,20);
  glVertex2f(990,20);
  glVertex2f(990,20);
  glVertex2f( 990,15);
  glVertex2f( 990,15);
  glVertex2f(10,15);
  glVertex2f(10,15);
  glVertex2f(10,20);  
 glEnd();

glBegin(GL_LINES);
   glVertex2f(800,20);//стовп
  glVertex2f(800,200);
  glVertex2f(800,200);
  glVertex2f( 805,200);
  glVertex2f( 805,200);
  glVertex2f(805,20);   
glEnd();
glBegin(GL_LINES); 
  glVertex2f(760,205);
  glVertex2f(840,205);
  glVertex2f(840,205);
  glVertex2f( 840,200);
  glVertex2f( 840,200);
  glVertex2f(760,200);
  glVertex2f(760,200);
  glVertex2f(760,205); 
  glEnd();
glBegin(GL_LINES); 
  glVertex2f(760,200);
  glVertex2f(765,200);
  glVertex2f(765,200);
  glVertex2f( 765,190);
  glVertex2f( 765,190);
  glVertex2f(760,190);
  glVertex2f(760,190);
  glVertex2f(760,200); 
  glEnd();
glBegin(GL_LINES); 
  glVertex2f(835,200);
  glVertex2f(840,200);
  glVertex2f(840,200);
  glVertex2f( 840,190);
  glVertex2f( 840,190);
  glVertex2f(835,190);
  glVertex2f(835,190);
  glVertex2f(835,200); 
  glEnd();
  glBegin(GL_LINES); //плафони 
  glVertex2f(750,190);
  glVertex2f(775,190);
  glVertex2f(775,190);
  glVertex2f( 775,175);
  glVertex2f( 775,175);
  glVertex2f(750,175);
  glVertex2f(750,175);
  glVertex2f(750,190); 
    glEnd();
  glBegin(GL_LINES); 
  glVertex2f(825,190);
  glVertex2f(850,190);
  glVertex2f(850,190);
  glVertex2f( 850,175);
  glVertex2f( 850,175);
  glVertex2f(825,175);
  glVertex2f(825,175);
  glVertex2f(825,190); 
    glEnd();
	
	

glutSwapBuffers();
}

void Timer(int)
{if(q<150){q+=3;}
if(z<50){z+=1;}

Draw();


glutTimerFunc(50,Timer,0);
}

void Initialize()
{
glClearColor(0.5,0.5,0.5,1.0);
glMatrixMode(GL_PROJECTION);
glLoadIdentity();
glOrtho(0,WinWid,0,WinHei,-200.0,200.0);
glMatrixMode(GL_MODELVIEW);
}

int main(int argc,char** argv)
{
glutInit(&argc,argv);
glutInitDisplayMode(GLUT_DOUBLE|GLUT_RGB);
glutInitWindowSize(WinWid,WinHei);
glutInitWindowPosition(100,200);
glutCreateWindow("I_Pro");
//reg
glutDisplayFunc(Draw);
glutTimerFunc(50,Timer,0);
Initialize();
glutMainLoop();

return 0;
}






#include <stdafx.h>
#include <gl\glut.h>
#include <math.h>

float WinWid=1000.0;
float WinHei=400.0;
int q=0;
int z=0;
int g=0;
int s=1;
int d=0;
int e=0;
int r=0;
int t=0;

void Draw()
{
glClear(GL_COLOR_BUFFER_BIT);
glColor3f(1.0,1.0,1.0);
glBegin(GL_LINE_LOOP); 

 for(int i = 0; i < 30; i++) //колесол
 { 
  float angle = 2.0 * 3.1415926 * float(i) / 30; 

  float dx = 10 * cosf(angle);
  float dy = 10 * sinf(angle);

  glVertex2f(130 + dx+q, 30 + dy);
}

 glEnd(); 
 glBegin(GL_LINE_LOOP); 

 for(int i = 0; i < 30; i++) //колесоп
 { 
  float angle = 2.0 * 3.1415926 * float(i) / 30; 

  float dx = 10 * cosf(angle);
  float dy = 10 * sinf(angle);

  glVertex2f(180 + dx+q, 30 + dy);
} glEnd();

  glBegin(GL_LINE_LOOP); //машинка
  glVertex2f(140+q,30);
   glVertex2f(170+q,30);
    glEnd(); 
glBegin(GL_LINE_LOOP);
glVertex2f(210+q,30);
   glVertex2f(190+q,30);
glEnd(); 
glBegin(GL_LINE_LOOP);
glVertex2f(210+q,30);
glVertex2f(210+q,45);
  glEnd(); 
glBegin(GL_LINE_LOOP);
glVertex2f(210+q,45);
glVertex2f(100+q,45); 
 glEnd(); 
 glBegin(GL_LINE_LOOP);
glVertex2f(100+q,45);
   glVertex2f(100+q,30);
glEnd(); 
glBegin(GL_LINE_LOOP);
glVertex2f(100+q,30);
   glVertex2f(120+q,30);
glEnd(); 
glBegin(GL_LINE_LOOP);
glVertex2f(155+q,65);
   glVertex2f(155+q,45);
glEnd(); 
glBegin(GL_LINE_LOOP);
glVertex2f(155+q,65);
   glVertex2f(190+q,65);
glEnd();
glBegin(GL_LINE_LOOP);
glVertex2f(190+q,65);
   glVertex2f(190+q,45);
glEnd();

glBegin(GL_LINE_LOOP); //качеля

 for(int i = 0; i < 30; i++) 
 { 
  float angle = 2.0 * 3.1415926 * float(i) / 30; 

  float dx = 12 * cosf(angle);
  float dy = 12 * sinf(angle);

  glVertex2f(500 + dx, 35 + dy);
} glEnd();
 glBegin(GL_LINES); 
  glVertex2f(360,50-z*0.5);
  glVertex2f(640,50+z*0.5);
  glVertex2f(640,50+z*0.5);
  glVertex2f( 640,46+z*0.5);
  glVertex2f( 640,46+z*0.5);
  glVertex2f(360,46-z*0.5);
  glVertex2f(360,46-z*0.5);
  glVertex2f(360,50-z*0.5); 
  glEnd();

glBegin(GL_LINES);  //земля
  glVertex2f(10,20);
  glVertex2f(990,20);
  glVertex2f(990,20);
  glVertex2f( 990,15);
  glVertex2f( 990,15);
  glVertex2f(10,15);
  glVertex2f(10,15);
  glVertex2f(10,20);  
 glEnd();

glBegin(GL_LINES);
   glVertex2f(800,20);//стовп
  glVertex2f(800,200);
  glVertex2f(800,200);
  glVertex2f( 805,200);
  glVertex2f( 805,200);
  glVertex2f(805,20);   
glEnd();
glBegin(GL_LINES); 
  glVertex2f(760,205);
  glVertex2f(840,205);
  glVertex2f(840,205);
  glVertex2f( 840,200);
  glVertex2f( 840,200);
  glVertex2f(760,200);
  glVertex2f(760,200);
  glVertex2f(760,205); 
  glEnd();
glBegin(GL_LINES); 
  glVertex2f(760,200);
  glVertex2f(765,200);
  glVertex2f(765,200);
  glVertex2f( 765,190);
  glVertex2f( 765,190);
  glVertex2f(760,190);
  glVertex2f(760,190);
  glVertex2f(760,200); 
  glEnd();
glBegin(GL_LINES); 
  glVertex2f(835,200);
  glVertex2f(840,200);
  glVertex2f(840,200);
  glVertex2f( 840,190);
  glVertex2f( 840,190);
  glVertex2f(835,190);
  glVertex2f(835,190);
  glVertex2f(835,200); 
  glEnd();
  glBegin(GL_LINES); //плафони
  glVertex2f(750*s,(190+g)*s);
  glVertex2f(775*s,(190+g)*s);
  glVertex2f(775*s,(190+g)*s);
  glVertex2f( 775*s,(175+g)*s);
  glVertex2f( 775*s,(175+g)*s);			
  glVertex2f(750*s,(175+g)*s);
  glVertex2f(750*s,(175+g)*s);
  glVertex2f(750*s,(190+g)*s); 
    glEnd();
    glBegin(GL_LINES); 
  glVertex2f(825*s,(190+g)*s);
  glVertex2f(850*s,(190+g)*s);
  glVertex2f(850*s,(190+g)*s);
  glVertex2f( 850*s,(175+g)*s);
  glVertex2f( 850*s,(175+g)*s);
  glVertex2f(825*s,(175+g)*s);
  glVertex2f(825*s,(175+g)*s);
  glVertex2f(825*s,(190+g)*s); 
    glEnd();
	glPolygonMode (GL_BACK, GL_LINE);
	glBegin(GL_QUADS);
	glVertex2f((750*e)-r,((20*e)+r)+t);
	glVertex2f((750*e)-r,((35*e)+r)+t);
	glVertex2f((762.5*e)-r,((35*e)+r)+t);
	glVertex2f((762.5*e)-r,((20*e)+r)+t);
	glEnd();
	glBegin(GL_QUADS);
	glVertex2f((762.5*e)+r,(20*e)+r);
	glVertex2f((762.5*e)+r,(35*e)+r);
	glVertex2f((775*e)+r,(35*e)+r);
	glVertex2f((775*e)+r,(20*e)+r);
	glEnd();
glutSwapBuffers();
}

void Timer(int)
{if(q<150){q+=3;}
if(z<50){z+=1;}
if(q>146&g>-155){g-=3;}
if(g<-150){s=0;}
if(s<=0){d=1;}
if(d>=1){e=1.0;}
if(e>=1.0){r+=5;}
if(r>=200){t-=6;}
Draw();


glutTimerFunc(50,Timer,0);
}

void Initialize()
{
glClearColor(0.5,0.5,0.5,1.0);
glMatrixMode(GL_PROJECTION);
glLoadIdentity();
glOrtho(0,WinWid,0,WinHei,-200.0,200.0);
glMatrixMode(GL_MODELVIEW);
}

int main(int argc,char** argv)
{
glutInit(&argc,argv);
glutInitDisplayMode(GLUT_DOUBLE|GLUT_RGB);
glutInitWindowSize(WinWid,WinHei);
glutInitWindowPosition(100,200);
glutCreateWindow("I_Pro");
//reg
glutDisplayFunc(Draw);
glutTimerFunc(50,Timer,0);
Initialize();
glutMainLoop();

return 0;
}
