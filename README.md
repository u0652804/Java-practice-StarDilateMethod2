# Java-practice-StarDilateMethod2

### Problem
請用程式畫出下列圖型

![demo](/image/demo.png)

### output
![demo](/image/demo.png)

### Java code
- dilate
```sh
	public void printStars(int layerNum) {
		
		char printData[] = new char[layerNum * 2 - 1];
		
		//init. printdata
		for(int i = 0; i < printData.length; i ++){
			if(i == layerNum - 1)
				printData[i] = '*';
			else
				printData[i] = ' ';
		}
		
		//print first row
		for(int j = 0; j < printData.length; j ++)
			System.out.print(printData[j]);
		System.out.println();
		
		char[] kernal1 = {' ', '*', ' '};
		char[] kernal2 = {'*', ' ', '*'};
		
		
		// use kernal1 trans data to kernal2
		for(int i = 0; i < layerNum - 1; i ++)
		{
			//dilate
			printData = dilater(kernal1, kernal2, printData);
			
			//print row
			for(int j = 0; j < printData.length; j ++)
				System.out.print(printData[j]);		
			System.out.println();
		}
		
	}
```

- dilate

```sh
	public char[] dilater(char[] kernal, char[] transData ,char[] original)
	{
		char[] out = new char[original.length];
		int[] neighbors = new int[kernal.length];
		
		//init. (copy data)
		for(int i = 0; i < original.length; i ++)
			out[i] = original[i];
		
		//init. neighbors
		for(int i = 0; i < kernal.length; i ++)
			neighbors[i] = i - kernal.length / 2;

		//dilate
		int kernalEdge = kernal.length / 2;
		for(int i = kernalEdge; i < original.length - kernalEdge; i ++){
			
			//judge equal or not with kernal
			boolean flag = true;
			for(int j = 0; j < neighbors.length; j ++){
				if(original[i + neighbors[j]] != kernal[j])
					flag = false;
			}
			
			//trans data to out[]
			if(flag)
			{
				for(int j = 0; j < neighbors.length; j ++){
					out[i + neighbors[j]] = transData[j];
				}
			}
		}
		
		return out;
	}
```


