# Leaf System Properties

### -DLeaf.library-download-repo
* default: not set

:	Use specified mirror repository for SpigotLibraryLoader instead of Maven Central.

### -DLeaf.nearestEntitySensorBucketCount
* default: 10

:	How many buckets will be used if entity count reached the Bucket Sort threshold.

	Should be the square root of entity count.

### -DLeaf.nearestEntitySensorBucketSortThresholdRatio
* default: 2.0

:	This value controls the ratio of Bucket Sort threshold (Threshold = bucketCount * ratio)

### -DLeaf.enableFMA
* default: false

: Whether to use Fused-Multiply-Add operations to accelerate math calculation.

	Requires a CPU which supports FMA instruction set, otherwise it will slower.

	You can use tools like [CPU-Z](https://www.cpuid.com/softwares/cpu-z.html) to check whehter your machine supports the FMA instruction set.
