
public class Table 
{
	int[][] table;
	boolean laplace;
	
	public Table(int i, int j)
	{
		table = new int[i][j];
		laplace = false;
	}
	
	public void toggleLaplace()
	{
		int d = 1;
		if(laplace)
		{
			d = -1;
		}
		for(int i = 0; i < table.length; i++)
		{
			for(int j = 0; j < table[i].length; j++)
			{
				table[i][j] += d;
			}
		}
		laplace = !laplace;
	}
	
	public void add(int i, int j)
	{
		table[i][j]++;
	}
	
	public int get(int i, int j)
	{
		return table[i][j];
	}
	
	public double getMLE(int i, int j)
	{
		return (double)table[i][j] / sum();
	}
	
	public void print()
	{
		for(int i = 0; i < table.length; i++)
		{
			for(int j = 0; j < table[i].length; j++)
			{
				System.out.print(table[i][j] + "  ");
			}
			System.out.println();
		}
	}
	
	private int sum()
	{
		int res = 0;
		for(int i = 0; i < table.length; i++)
		{
			for(int j = 0; j < table[i].length; j++) 
			{
				res += table[i][j];
			}
		}
		return res;
	}
}
