# tirakan
fb tirakan
import java.util.*;
public class sofyan {
	private static String kata[] = new String[1000];
	private static String newkata[] = new String[1000];
	
	// methode untuk mengecek kata yg sama
	public static boolean ckKata(int n, String x)
	{
		// inisialisasi
			boolean ketemu=false;
			
			for (int i=0; i <n; i++)
			{
				//jika ada yg sama
				if (kata[i].equalsIgnoreCase(x))
				{
					ketemu=true;
					break;
				}
			}
			return ketemu;	
	}

	public static void main (String args[])
	{
		//array
		int jumkata[] = new int[1000];
		int indeks[] = new int[1000];
		
		//inisialisasi variabel
		
		String teks, temp="";
		boolean ketemu=false;
		int a, k, n, m, count=0, jum;
		
		//inputen dari keyboard
		System.out.print("Masukkan kalimat = ");
		Scanner obj = new Scanner(System.in);
		teks = obj.nextLine();
		
		// menentukan kata
		for (int i = 0; i<teks.length(); i++)
		{
			// jika di temukan spasi
			if (teks.charAt(i)==' ')
			{
				count+=1;
				temp="";
				
			}
			else
			{
				temp = temp + teks.charAt(i);
				kata[count] = temp;
			}
		}
		n=count+1;// banyaknya kata dalam suatu kalimat
		
		// eliminasi kata yang sama
		k=0; a=0;
		for (int i=0; i < n; i++)
		{
			if (!ckKata(a, kata[i]))
			{
				//bentuk kata baru dalam array
				newkata[k] = kata[i];
				k++;
				
			}
			a++;
		}
		m=k; //banyaknya kata ya telh dieliminasi
		// proses penghitungan kata dalam suatu kalimat
		for (int i=0; i < m; i++)
		{
			jum=0;
			for (int j=0; j < n; j++)
			{
				if (newkata[i].equalsIgnoreCase(kata[j]))
					jum+=1;
				
			}
			System.out.print("kata = "+newkata[i]+
						" jumlahnya "+jum);
		}
		
	}
}



