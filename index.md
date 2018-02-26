#### 复制数组
##### 1.copyOf(arr,int newLength)
复制指定的数组，截断或填充0/null/false（如有必要），因此副本具有指定的长度。对于原始数组和副本都有效的所有索引，两个数组将包含相同的值。对于在副本中而不是原件有效的任何索引，副本将包含0/null/false。当且仅当指定长度大于原始数组的长度时，这些索引才会存在。
##### copyOfRange(arr,int formIndex,int toIndex)
将指定数组的指定范围复制到新数组中。 范围（ from ）的初始指数必须介于零和original.length之间（ from）。original[from]的值被放置在副本的初始元素中（除非是from == original.length或from == to）。原始数组中后续元素的值将被放置在副本中的后续元素中。 范围（ to ）的最终指数（ to）必须大于或等于from，可能大于original.length ，在这种情况下， false被放置在索引大于或等于original.length -from的副本的所有元素中。 返回的数组的长度将为to - from 。 

#### 数组查询
##### 1.binarySearch(Obkect[],Object key)
使用二进制搜索算法搜索指定值的指定字节数组。 在进行此调用之前，必须对数组进行排序（按照Arrays.sort(Object[])方法）。 如果没有排序，结果是未定义的。 如果数组包含具有指定值的多个元素，则不能保证将找到哪个元素。 

```
int arr[] = new int[]{5,8,423,45,4,561,6,486,43,564,8,168,4,44,};
Arrays.sort(arr);
int index = Arrays.binarySearch(arr, 44);
System.out.println(index);
for(int i = 0;i<arr.length;i++) {
	System.out.print(arr[i] + " ");
}
```
##### 2.binarySearch(Object[],int fromIndex,int toIndex,Object key)
使用二进制搜索算法搜索指定值的指定字节数组的范围。在进行此呼叫之前，范围必须按照sort(byte[], int,int)方法进行排序。 如果没有排序，结果是未定义的。 如果范围包含具有指定值的多个元素，则不能保证将找到哪个元素。
#### 冒泡排序

```
	int arr[] = new int[] { 5, 8, 423, 45, 4, 561, 6, 486, 43, 564, 8, 168, 4, 44, };
	for (int i = 0; i < arr.length; i++) {
		for (int j = 0; j < arr.length - i - 1; j++) {
			if (arr[j] > arr[j + 1]) {
				int temp = arr[j];
				arr[j] = arr[j + 1];
				arr[j + 1] = temp;
			}
		}
	}
	for (int k = 0; k < arr.length; k++) {
		System.out.print(arr[k] + " ");
	}
	System.out.println("\n" + arr.length);
```
#### 直接选择排序

```
for (int i = 1; i < arr.length; i++) {
			int index = 0;
	for (int j = 1; j <= arr.length - i ; j++) {
		if (arr[j] > arr[index]) {
			index = j;
		}
	}
	int temp = arr[arr.length - i];
	arr[arr.length - i] = arr[index];
	arr[index] = temp;
}
```
#### 反转排序
把前后最两边的值交换，然后再换里面的两边，依次，直到交换到了中间。

```
		//反转排序
		int temp;
		int len = arr.length;
		for(int i = 0;i<len/2;i++) {
			temp = arr[i];
			arr[i] = arr[len - i - 1];
			arr[len - i - 1]=temp;
		}
		for (int k = 0; k < arr.length; k++) {
			System.out.print(arr[k] + " ");
		}
		System.out.println("\n" + arr.length);
```
