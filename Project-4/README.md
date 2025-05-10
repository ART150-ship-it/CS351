## Project-4 Results 


### iota.cu
##### This is a CUDA-accelerated iota function
```bash
__global__
void iota(size_t n, DataType* values, const DataType startValue){
        int i = blockIdx.x * blockDim.x + threadIdx.x;
        if(i > n) return;
        values[i] = i + startValue;
}
```
#### Question 1: I can speculate that the reason why CUDA does not seem to be a good soultion to this problem could be just setting up the threads is more work than just doing it the normal CPU way. 

### julia.cu
##### This is the CUDA kernel that enables the program to draw a julia set.
```bash
__global__
void julia(Complex d, Complex center, Color* pixels) {
    int x = blockIdx.x * blockDim.x + threadIdx.x;
    int y = blockIdx.y * blockDim.y + threadIdx.y;
    for (; y < Height; ++y) {
        for (; x < Width; ++x) {
            Complex c(x*d.x, y*d.y);
            c -= center;
            Complex z;

            int iter = 0;
            while (iter < MaxIterations && magnitude(z) < 2.0) {
                z = z*z + c;
                ++iter;
            }

            pixels[x + y * Width] = setColor(iter);
        }
    }
}
```

## Pretty Image from (-0.253, 0.524)
![Generated from -0.253, 0.524](<julia copy.jpeg>)
