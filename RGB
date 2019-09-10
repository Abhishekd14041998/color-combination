	/*An Interactive Program to create 3d objects*/
 

#include<string.h>
#include<stdarg.h>
#include<stdio.h>
#include<GL/glut.h>
static double x=0.0;
static float red1=0; 
static float green1=0;
static float blue1=0;
static float help1=1;
void *currentfont;

void setFont(void *font)
{
	currentfont=font;
}

void drawstring(float x,float y,float z,char *string)
{
	char *c;
	glRasterPos3f(x,y,z);
 
	for(c=string;*c!='\0';c++)
	{	glColor3f(0.0,1.0,1.0);
		glutBitmapCharacter(currentfont,*c);
	}
}

void stroke_output(GLfloat x, GLfloat y, char *format,...)
{
	va_list args;
	char buffer[200],*p;
	va_start(args, format);
	vsprintf(buffer, format, args);
	va_end(args);
	glPushMatrix();
	glTranslatef(-2.5, y, 0);
	glScaled(0.003, 0.005, 0.005);
	for (p = buffer; *p; p++)
    glutStrokeCharacter(GLUT_STROKE_ROMAN, *p);
	glPopMatrix();
}


void doInit() 
{
    
	/* Background and foreground color */
    glClearColor(0.5,0.5,0.5,0.0);
    glColor3f(1.0,1.0,1.0);
    glViewport(0,0,640,480);
 
	/* Select the projection matrix and reset it then
     setup our view perspective */
    glMatrixMode(GL_PROJECTION);
    glLoadIdentity();
    gluPerspective(30.0f,(GLfloat)640/(GLfloat)480,0.1f,200.0f);    
    /* Select the modelview matrix, which we alter with rotatef() */
    glMatrixMode(GL_MODELVIEW);
    glLoadIdentity();
    glClearDepth(2.0f);
    glEnable(GL_DEPTH_TEST);
	glEnable(GL_COLOR_MATERIAL);
    glDepthFunc(GL_LEQUAL);
}



void torch(){

glPushMatrix();
glutSolidSphere(0.8,50,50);
glPopMatrix();

glPushMatrix();
glRotatef(90,0,1,0);
glScaled(0.5,0.5,3);
glColor3f(0,1,1);
glutSolidTorus(0.4,1.5,50,50);
glPopMatrix();


glPushMatrix();
glTranslatef(-1.5,0,0);
glRotatef(90,0,1,0);
glScaled(0.7,0.7,1.5);
glutSolidTorus(0.4,1.5,50,50);
glPopMatrix();



}


void help(){

glClear(GL_COLOR_BUFFER_BIT | GL_DEPTH_BUFFER_BIT);

glPushMatrix();
glScaled(0.7,0.7,0.7);
stroke_output(-2,3,"H --> Toggle Help");
stroke_output(-2,2,"R --> Toggle Red Light");
stroke_output(-2,1,"G --> Toggle Green Light");
stroke_output(-2,0,"B --> Toggle Blue Light");
glPopMatrix();




glFlush();
glutSwapBuffers();
}



void draw(){
	glClear(GL_COLOR_BUFFER_BIT | GL_DEPTH_BUFFER_BIT);
	glLoadIdentity();
	glTranslatef(0.0f,0.0f,-13.0f);
	

glPushMatrix();
glTranslatef(0,0,-15);
glScaled(1,1,0.1);
glColor3f(0.1,1.0,1.0);
glutSolidCube(9);
glPopMatrix();


glPushMatrix();
glColor3f(0.1,1,1);
glutSolidCone(4.5,15,40,40);
glPopMatrix();


// Color Sphere

glPushMatrix();
glTranslatef(0,0,-14);
glScaled(1,1,0.1);

glColor3f(red1,green1,blue1);

glutSolidSphere(2,30,30);
glPopMatrix();

// red Torch
glPushMatrix();
glTranslatef(-1.5,-2,2);
glRotatef(-20,0,0,1);
glPushMatrix();
glRotatef(90,0,1,0);
glScaled(0.3,0.3,0.3);
glColor3f(1.0,0.0,0.0);
torch();
glPopMatrix();
glPopMatrix();


if(red1){
glPushMatrix();
glRotatef(50,1,0,1);
glRotatef(-55,0,1,1);
glColor3f(1.0,0.0,0.0);
glutWireCone(1.0,3,10,10);
glPopMatrix();
}



// Green Torch
glPushMatrix();
glTranslatef(0,-2,2);
glRotatef(-20,0,0,1);
glPushMatrix();
glRotatef(90,0,1,0);
glScaled(0.3,0.3,0.3);
glColor3f(0.0,1.0,0.0);
torch();
glPopMatrix();
glPopMatrix();

if(green1){
glPushMatrix();
glTranslatef(0,-0.5,-3);
glRotatef(10,1,0,1);
glColor3f(0.0,1.0,0.0);
glutWireCone(1.0,7,10,10);
glPopMatrix();

}

// Blue Torch
glPushMatrix();
glTranslatef(1.5,-2,2);
glRotatef(-20,0,0,1);
glPushMatrix();
glRotatef(90,0,1,0);
glScaled(0.3,0.3,0.3);
glColor3f(0.0,0.0,1.0);
torch();
glPopMatrix();
glPopMatrix();

if(blue1){
glPushMatrix();
glRotatef(90,1,0,1);
glColor3f(0.0,0.0,1.0);
glutWireCone(1.0,3,10,10);
glPopMatrix();
}


glFlush();
glutSwapBuffers();
}


void doDisplay()
{
	glClear(GL_COLOR_BUFFER_BIT | GL_DEPTH_BUFFER_BIT);
	glLoadIdentity();
	glTranslatef(0.0f,0.0f,-13.0f);
	glClearColor(0.0,0.0,0.0,0.0);
	glClear(GL_COLOR_BUFFER_BIT | GL_DEPTH_BUFFER_BIT);
	glLoadIdentity();
	glTranslatef(0.0f,0.0f,-13.0f);
	
	setFont(GLUT_BITMAP_TIMES_ROMAN_24);
	glColor3f(0,0,1);
	drawstring(-0.7,3,0.0,"SDMIT UJIRE");
	setFont(GLUT_BITMAP_TIMES_ROMAN_24);
	glColor3f(1,0,1);
	drawstring(-2.2,2.5,0.0,"DEPARTMENT OF COMPUTER SCIENCE AND ENGINEERING");
	setFont(GLUT_BITMAP_TIMES_ROMAN_24);
    glColor3f(1,0.5,1);
	drawstring(-1,2,0,"MINI PROJECT ON ");
setFont(GLUT_BITMAP_TIMES_ROMAN_24);
    glColor3f(1,0.5,0.5);
	drawstring(-1.3,1.5,0,"COLOR COMBNATION ");
	setFont(GLUT_BITMAP_TIMES_ROMAN_24);
    glColor3f(0.0,1.0,1.0);
	drawstring(-0.5,1,0,"By");

	setFont(GLUT_BITMAP_TIMES_ROMAN_24);
    glColor3f(0.0,1.0,1.0);
	drawstring(-2,.5,0,"ABHISHEK D                           4SU16CS004 ");

	setFont(GLUT_BITMAP_TIMES_ROMAN_24);
    glColor3f(0.0,1.0,1.0);
	drawstring(-2,.0,0,"ABHISHEK M                          4SU16CS005 ");
	setFont(GLUT_BITMAP_TIMES_ROMAN_24);
    glColor3f(0.0,1.0,1.0);
	drawstring(-0.5,-.5,0,"GUIDED By");

setFont(GLUT_BITMAP_TIMES_ROMAN_24);
    glColor3f(0.0,1.0,1.0);
	drawstring(-0.1,-1,0,"PROF.SNEHA SHETTY");
setFont(GLUT_BITMAP_TIMES_ROMAN_24);
    glColor3f(0.0,1.0,1.0);
	drawstring(-0.1,-1.5,0,"PROF.RAKSHITH M D");
setFont(GLUT_BITMAP_TIMES_ROMAN_24);
    glColor3f(0.0,1.0,1.0);
	drawstring(-0.1,-2,5,"PRESS S TO START AND Q TO QUIT");



	/*stroke_output(-2.0, -1, "s --> Start");
	stroke_output(-2.0, -1.75, "A --> About");
	stroke_output(-2.0, -3,"q --> Quit");

*/
	// Write your Own Code Here


	//if(help1)
	//	help();
	//else
	//draw();




	GLfloat mat_ambient[]={0.0f,1.0f,2.0f,1.0f};
	GLfloat mat_diffuse[]={0.0f,1.5f,.5f,1.0f};
	GLfloat mat_specular[]={5.0f,1.0f,1.0f,1.0f};
	GLfloat mat_shininess[]={100.0f};
	glMaterialfv(GL_FRONT,GL_AMBIENT,mat_ambient);
	glMaterialfv(GL_FRONT,GL_DIFFUSE,mat_diffuse);
	glMaterialfv(GL_FRONT,GL_SPECULAR,mat_specular);
	glMaterialfv(GL_FRONT,GL_SHININESS,mat_shininess);

	/*GLfloat lightIntensity[]={3.7f,0.7f,0.7f,1.0f};     Orange
	GLfloat light_position[]={2.0f,5.0f,3.0f,1.0f};*/

	/*light source properties*/
	GLfloat lightIntensity[]={1.7f,1.7f,1.7f,1.0f};
	GLfloat light_position[]={2.0f,0.0f,0.0f,0.0f};
	glLightfv(GL_LIGHT0,GL_POSITION,light_position);
	GLfloat light_position2[]={0.0f,0.0f,8.0f,0.0f};
	glLightfv(GL_LIGHT0,GL_POSITION,light_position2);

	GLfloat light_position3[]={6.0f,0.0f,5.0f,0.0f};
	
	glLightfv(GL_LIGHT0,GL_POSITION,light_position3);
	glLightfv(GL_LIGHT0,GL_DIFFUSE,lightIntensity);



	glFlush();
	glutSwapBuffers();
    
}

void mykey(unsigned char key,int x,int y)
{
	if(key=='q'||key=='Q')
	{
		exit(0);
	}

	
	if(key=='h'||key=='H')
	{
		help1=!help1;
		glutPostRedisplay();
	}


	if(key=='s' || key=='S'){
	
	
	glutIdleFunc(draw);
	
	
	}


	if(key=='r'||key=='R')
	{
		red1=!red1 ;
		glutPostRedisplay();
	}

	if(key=='g'||key=='G')
	{
		green1=!green1;
		glutPostRedisplay();
	
	}

	if(key=='b'||key=='B')
	{
		blue1=!blue1;
		glutPostRedisplay();
	
	}


}

int main(int argc, char *argv[]) 
{
    glutInit(&argc, argv);
    glutInitDisplayMode(GLUT_DOUBLE|GLUT_RGB);
    glutInitWindowSize(640,480);
    glutInitWindowPosition(0,0);
    glutCreateWindow("Color Combination");
    glutDisplayFunc(doDisplay);
	glEnable(GL_LIGHTING);
	glEnable(GL_LIGHT0);
	glShadeModel(GL_SMOOTH);
	glEnable(GL_DEPTH_TEST);
	glEnable(GL_NORMALIZE);

	glutKeyboardFunc(mykey);
	doInit();
    glutMainLoop();
	return 0; 
}
