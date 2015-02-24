// life.cpp : Defines the entry point for the console application.
//

#include "stdafx.h"
#include <iostream>
#include "screen.h"

using namespace std;

const int Y_SIZE = 22;

void display(char[][Y_SIZE]);
void generation(char[][Y_SIZE]);

int _tmain(int argc, _TCHAR* argv[])
{
	char world[75][22];

	world[12][12] = true;
	world[13][13] = true;
	world[13][11] = true;
	world[14][12] = true;
	world[15][13] = true;
	world[16][13] = true;
	world[16][12] = true;
	world[16][10] = true;
	world[17][13] = true;
	world[18][12] = true;
	world[18][13] = true;
	world[19][10] = true;
	world[19][11] = true;
	world[19][11] = true;
	world[19][12] = true;
	world[20][13] = true;
	world[21][12] = true;
	world[21][11] = true;
	world[22][10] = true;
	world[23][11] = true;
	world[24][13] = true;
	world[24][12] = true;
	world[25][12] = true;
	world[26][12] = true;
	world[26][13] = true;
	world[29][12] = true;
	world[29][11] = true;
	world[29][10] = true;
	world[29][10] = true;
	world[30][12] = true;
	world[30][11] = true;
	world[31][13] = true;
	world[32][13] = true;
	world[32][11] = true;
	world[32][11] = true;
	world[33][12] = true;
	world[34][13] = true;
	world[35][10] = true;
	world[35][10] = true;
	world[36][13] = true;
	world[37][11] = true;
	world[37][12] = true;
	world[38][12] = true;
	world[38][11] = true;
	world[38][13] = true;
	world[38][12] = true;
	world[38][11] = true;
	world[39][10] = true;
	world[40][10] = true;
	world[40][10] = true;
	world[41][11] = true;
	world[41][12] = true;
	world[42][13] = true;
	world[42][11] = true;
	world[42][12] = true;
	world[43][10] = true;

	generation(world);
	
	system("pause > NULL");
	return 0;
}

void display(char arr[][Y_SIZE])
{
	char character = 1;

	for (int i = 0; i < 75; i++)
	{
		for (int j = 0; j < 22; j++)
		{
			if (arr[i][j] == true)
			{
				gotoxy(i, j);
				cout << character;
				
			}
		}
	}

	delay(1000);
	system("CLS");
}

void generation(char arr[][Y_SIZE])
{
	for (int i = 1; i < 75; i++)
	{
		for (int j = 1; j < 22; j++)
		{
			if (arr[i][j] == true)
			{
				if (arr[i + 1][j + 1] == true && arr[i + 1][j] == true && arr[i][j - 1] == true)
					arr[i][j] == true;
				if (arr[i + 1][j] == true && arr[i + 1][j + 1] == true && arr[i][j - 1] == true)
					arr[i][j] == true;
				
				
			}

			if (arr[i][j] == false)
			{
				if (j + 1 == true && j + 1 == true && i + 1 == true)
					arr[i][j] == true;
				if (j + 1 == true && j + 1 == true && i - 1 == true)
					arr[i][j] == true;
				if (j + 1 == true && j - 1 == true && i + 1 == true)
					arr[i][j] == true;
				if (j + 1 == true && j - 1 == true && i - 1 == true)
					arr[i][j] == true;
				if (j - 1 == true && j + 1 == true && i + 1 == true)
					arr[i][j] == true;
				if (j - 1 == true && j + 1 == true && i - 1 == true)
					arr[i][j] == true;
				if (j - 1 == true && j - 1 == true && i + 1 == true)
					arr[i][j] == true;
				if (j - 1 == true && j - 1 == true && i - 1 == true)
					arr[i][j] == true;

				if (j + 1 == false && j + 1 == false && i + 1 == false)
					arr[i][j] == false;
				if (j + 1 == false && j + 1 == false && i - 1 == false)
					arr[i][j] == false;
				if (j + 1 == false && j - 1 == false && i + 1 == false)
					arr[i][j] == false;
				if (j + 1 == false && j - 1 == false && i - 1 == false)
					arr[i][j] == false;
				if (j - 1 == false && j + 1 == false && i + 1 == false)
					arr[i][j] == false;
				if (j - 1 == false && j + 1 == false && i - 1 == false)
					arr[i][j] == false;
				if (j - 1 == false && j - 1 == false && i + 1 == false)
					arr[i][j] == false;
				if (j - 1 == false && j - 1 == false && i - 1 == false)
					arr[i][j] == false;
			}		
		}
	}

	display(arr);
	
}
