### Hi there 👋

- I'm Tsingyun, living in Hangzhou

```java
public class Demo10 { 
    public static void main(String[] args) {
		Integer[] nums = Utils.generateArr(100, 30);
		sort(nums);
		Utils.printArr(nums);
		System.out.println(Utils.isPositiveOrder(nums));
	}

	private static void sort(Integer[] nums) {
		// 1. 对数组建堆
		heapify(nums);
		int heapSize = nums.length;
		while (heapSize > 1) {
			--heapSize;
			Utils.swap(nums, 0, heapSize);
			shiftDown(nums, heapSize, 0);
		}
	}

	private static void heapify(Integer[] nums) {
		int lastIndex = nums.length - 1;
		int lastNonLeftIndex = (lastIndex - 1) >> 1;
		for (int i = lastNonLeftIndex; i >= 0; i--) {
			shiftDown(nums, nums.length, i);
		}
	}

	@SuppressWarnings("DuplicatedCode")
	private static void shiftDown(Integer[] nums, int n, int i) {
		int num = nums[i];
		int half = n >> 1;
		while (i < half) {
			// childIndex 默认取左子节点
			int childIndex = (i << 1) + 1;
			int rightChildIndex = childIndex + 1;
			if (rightChildIndex < n && nums[rightChildIndex] > nums[childIndex]) {
				childIndex = rightChildIndex;
			}
			if (num > nums[childIndex]) {
				break;
			}
			nums[i] = nums[childIndex];
			i = childIndex;
		}
		nums[i] = num;
	}
}

```

<!--
![8F7650DA-F9CC-4AAC-92DF-D4AD569C7ED7_1_105_c](https://user-images.githubusercontent.com/56377217/187681840-7db15c7c-9829-473e-a550-1d1972983d13.jpeg)

**imtsingyun/imtsingyun** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:


- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->
