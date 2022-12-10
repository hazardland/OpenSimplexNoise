# OpenSimplexNoise

A C++ port of Open Simplex Noise. The port is based on a implementation in Java by Kurt Spencer.
The implementation includes 2D, 3D and 4D noise.

## Example
Example animation made by the noise.

![](/Examples/animation.gif)

## Usage
Add the .h and .cpp file to your project.
```cpp
OpenSimplexNoise::Noise noise
double value = noise.eval(0.13, 0.31) // For 2D noise
```

## Usage 2
The example is library usage code fragment for those who might be lost
```
    void update(State* state) {
        if (SDL_GetTicks()-ticks>100) {
            int alpha;
            srand(clock());
            OpenSimplexNoise::Noise noise{rand()}; // Init
            for (int y=0; y<512; y++) {
                for (int x=0; x<512; x++)
                {
                    alpha = (noise.eval(x*0.01, y*0.01) + 1) / 2.0  * 255.0; // Use
                    minimap->setPixel(x, y, 255, 255, 255, alpha);
                }

            }
            ticks = SDL_GetTicks();
        }
    }
```
