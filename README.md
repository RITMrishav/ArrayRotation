# ArrayRotation
import java.util.Arrays;

public class ArrayRotation {
    public static void main(String[] args) {
        int[] arr = {1, 2, 3, 4, 5};
        int rotationCount = 2;

        System.out.println("Input Array: " + Arrays.toString(arr));
        rotateArray(arr, rotationCount);
        System.out.println("Rotated Array: " + Arrays.toString(arr));
    }

    public static void rotateArray(int[] arr, int rotationCount) {
        int length = arr.length;
        rotationCount %= length;  // To handle rotation counts larger than the array length

        reverse(arr, 0, length - 1);  // Reverse the whole array
        reverse(arr, 0, rotationCount - 1);  // Reverse the first part
        reverse(arr, rotationCount, length - 1);  // Reverse the second part
    }

    private static void reverse(int[] arr, int start, int end) {
        while (start < end) {
            int temp = arr[start];
            arr[start] = arr[end];
            arr[end] = temp;
            start++;
            end--;
        }
    }
}
