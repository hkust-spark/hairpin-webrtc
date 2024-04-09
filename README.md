# The WebRTC Implementation of Hairpin (NSDI 2024)
Welcome! Besides the simulation codes in [](), we provide a WebRTC-compatible implementation of Hairpin based on the M119 release of WebRTC.
This is a preliminary implementation and not fully tested yet.
We are working on a more stable version but please do let us know if you encounter any issues.

## How to patch Hairpin over WebRTC

### Step 1: Clone the WebRTC repository
Please follow the [official instructions](https://webrtc.github.io/webrtc-org/native-code/development/) to clone the WebRTC repository.

### Step 2: Clone the current repository
If you follow the instructions above, you should under the `webrtc-checkout` directory.
```
git clone https://github.com/hkust-spark/hairpin-webrtc.git
```

### Step 3: Switch to the M119 release
If you follow the instructions above, you should under the `webrtc-checkout` directory.
```
cd src/
git checkout -b my_branch refs/remotes/branch-heads/6045
```

### Step 4: Apply the patch
Make sure that you are at the `src` directory of the WebRTC repository.
```
git apply ../hairpin-webrtc/hairpin.patch
```
Reminder: you can add the `--stat` option to see the changes, and `--check` option to do a dry run to detect errors beforehand.

### Step 5: Copy the weights of Hairpin
Copy the weights of Hairpin (`fec_rate_table.bin`) to the `src` directory of the WebRTC repository.
```
cp ../hairpin-webrtc/fec_rate_table.bin .
```

## Questions
If you have any questions, please feel free to contact us at [Zili Meng](mailto:zilim@ust.hk) and [Yan Zhang](zh-yan20@mails.tsinghua.edu.cn).