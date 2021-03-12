#include<stdio.h>

int connect[8][8] ={  //初始化各点的连通性
	{0,1,0,1,1,0,2,0},
	{1,0,1,0,0,1,0,2},
	{0,1,0,1,2,0,1,0},
	{1,0,1,0,0,2,0,1},
	{1,0,2,0,0,1,0,1},
	{0,1,0,2,1,0,1,0},
	{2,0,1,0,0,1,0,1},
	{0,2,0,1,1,0,1,0},
};
int isCon(int, int*);
void printSub(int, int);
int isE(int, int*);
int main()
{
	int n[8];
	int a, i, j, k;
	for (i = 0; i < 8; i++)
	{
		scanf_s("%d", &n[i]);
	}
	if ((n[0] + n[5] + n[7] + n[2]) - (n[1] + n[3] + n[4] + n[6]) != 0)
	{
		printf("IMPOSSIBLE\n");
	}
	else {
		for (i = 0; i < 8; i++)
		{
			while (n[i] != 0 && isCon(i, n))
			{
				for (int j = 0; j < 8; j++)
				{
					if (connect[i][j] == 1 && n[j] != 0)
					{
						n[i]--;
						n[j]--;
						printSub(i, j);
						break;
					}
				}
			}
		}
		//
		for (i = 0; i < 8; i++)
		{
			int k;
			while (n[i] != 0&&isE(i,n))
			{
				for (int j = 0; j < 8; j++)
				{
					if (connect[i][j] == 2 && n[j] != 0)
					{
						n[i]--;
						n[j]--;
						int x;
						if (i == 0)
							x = i + 1;
						else {
							x = i - 1;
						}
						for (k = 0; k < 8; k++)
							if (connect[x][k] == 1 && connect[j][k]==1)
							{
								break;
							}
						printf("%c%c+\n", 'A' + x, 'A' + k);
						printf("%c%c-\n", 'A' + x, 'A' + i);
						printf("%c%c-\n", 'A' + j, 'A' + k);
						break;
					}
				}
			}
		}
	}
}
int isE(int a, int* n)
{
	for (int i = 0; i < 8; i++)
	{
		if (connect[a][i] == 2 && n[i] != 0)
			return 1;
	}
	return 0;
}
void printSub(int a, int b)
{
	printf("%c%c-\n", 'A' + a, 'A' + b);
}
int isCon(int a, int* n)
{
	for (int i = 0; i < 8; i++)
	{
		if (connect[a][i] == 1 && n[i] != 0)
			return 1;
	}
	return 0;
}
