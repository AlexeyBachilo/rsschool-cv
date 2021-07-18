# CV
###Name:
 Alexey
###Surname:
 Bachilo
###Contacts: 

* +375447918354 (A1)
* https://vk.com/brocrash
* @BroCrash (Telegram)
* @brocrash (Instagram)
* https://github.com/AlexeyBachilo

###Info: 
I want to become a Junior Developer on Javascript. My aim is to improve my knowledge and skills, achieve different heights in several branches. I'm punctual, easy-going and hard-working and always down to help, if needed. I don't have any working experience yet, but I have a desire to learn new things and I'm determined to develop myself in terms of job, personality and art.

###Skills: 
* ######HTML/CSS
*  ######C++
*  ######Git
*  ######C
*  ######C'#'


###C++ Code Example:
```C
#include <iostream>
#include <fstream>
#include <cassert>
using std::endl;
using std::cout;
using std::cin;
using std::ifstream;
using std::ofstream;

struct pixel{
	unsigned char red;
	unsigned char green;
	unsigned char blue;
};//A

void shift(pixel& a) {
	unsigned char save = a.red;
	a.red = a.green;
	a.green = a.blue;
	a.blue = save;
}//A

void inversion(pixel& a) {
	a.blue = 255 - a.blue;
	a.green = 255 - a.green;
	a.red = 255 - a.red;
}//A

void blue_color_channel(pixel& a) {
	a.red = 0;
	a.green = 0;
}//A

void green_color_channel(pixel& a) {
	a.red = 0;
	a.blue = 0;
}//A

void red_color_channel(pixel& a) {
	a.blue = 0;
	a.green = 0;
}//A

void monochrome(pixel& a) {
	unsigned char common = (a.blue + a.green + a.red) / 3;
	a.blue = common;
	a.green = common;
	a.red = common;
}//A

void pop_art(pixel& a) {
	unsigned char common = (a.blue + a.green + a.red) / 3;
	if (common < 100) {
		a.red = 178;
		a.green = 58;
		a.blue = 204;
	}
	else {
		a.red = 255;
		a.green = 207;
		a.blue = 72;
	}
}//A

void picture(const char* name1, const char* name2, void (*change)(pixel&)) {
	ifstream in(name1, std::ios::binary);
	ofstream out(name2, std::ios::binary);
	assert(in.is_open());
	int w, h;
	in.read((char*)&w, 4);
	in.read((char*)&h, 4);
	out.write((char*)&w, 4);
	out.write((char*)&h, 4);
	for (int i = 0; i < h; i++) {
		for (int j = 0; j < w; j++) {
			pixel a;
			in.read((char*)&a.blue, 1);
			in.read((char*)&a.green, 1);
			in.read((char*)&a.red, 1);
			change(a);
			out.write((char*)&a.blue, 1);
			out.write((char*)&a.green, 1);
			out.write((char*)&a.red, 1);
		}
	}
}//B

void gradient(pixel& a, double grad) {
	a.red = 255 - (255 - a.red) * (1 - grad);
	a.green = 255 - (255 - a.green) * (1 - grad);
	a.blue = 255 - (255 - a.blue) * (1 - grad);
}//C

void picture_gradient(const char* name1, const char* name2, bool direction) {
	ifstream in(name1, std::ios::binary);
	ofstream out(name2, std::ios::binary);
	assert(in.is_open());
	int w, h;
	in.read((char*)&w, 4);
	in.read((char*)&h, 4);
	out.write((char*)&w, 4);
	out.write((char*)&h, 4);
	if (direction == 1) {
		for (int i = 0; i < h; i++) {
			for (int j = 0; j < w; j++) {
				pixel a;
				double grad = (double)i / h;
				in.read((char*)&a.blue, 1);
				in.read((char*)&a.green, 1);
				in.read((char*)&a.red, 1);
				gradient(a, grad);
				out.write((char*)&a.blue, 1);
				out.write((char*)&a.green, 1);
				out.write((char*)&a.red, 1);
			}
		}
	}
	else {
		for (int i = 0; i < h; i++) {
			for (int j = 0; j < w; j++) {
				pixel a;
				double grad = 1 - (double)i / h;
				in.read((char*)&a.blue, 1);
				in.read((char*)&a.green, 1);
				in.read((char*)&a.red, 1);
				gradient(a, grad);
				out.write((char*)&a.blue, 1);
				out.write((char*)&a.green, 1);
				out.write((char*)&a.red, 1);
			}
		}
	}
	
}//C



int main() {
	picture("butterfly.img", "butterfly1.img", shift);
	picture("butterfly.img", "butterfly2.img", inversion);
	picture("butterfly.img", "butterfly3.img", blue_color_channel);
	picture("butterfly.img", "butterfly4.img", green_color_channel);
	picture("butterfly.img", "butterfly5.img", red_color_channel);
	picture("butterfly.img", "butterfly6.img", monochrome);
	picture("butterfly.img", "butterfly7.img", pop_art);
	picture_gradient("butterfly.img", "butterfly8.img",1);
}
```

###Experience:
I don't have any working experience yet.

###Education:
Belarusian State University, Faculty of Radiophysics and Computer Technologies; Comp-As cources (HTML\CSS, C, C#); BelGameDev meet-ups (game-development, advertisement, etc.)

###English:
I suppose that my English level is around C1. (I've been learning and practicing it for 13 years).
