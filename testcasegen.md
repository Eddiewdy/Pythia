## 创建champsim测试

1. set environment variables
    ```bash
    source setvars.sh
    ```

2. download the traces
    ```bash
    cd ../scripts
    perl download_traces.pl --csv artifact_traces"your trace file".csv --dir ../traces/
    ```
3. generate jobfile, you can find your prefetch setup in`$(PYTHIA_HOME)/config/`
    ```bash
    cd $PYTHIA_HOME/experiments/
    perl ../scripts/create_jobfile.pl --exe $PYTHIA_HOME/bin/perceptron-multi-multi-no-ship-1core --tlist MICRO21_1C"your task list".tlist --exp MICRO21_1C"your exp file".exp --local 1 > jobfile.sh
    ```
4. run the simulation
    ```bash
    cd $PYTHIA_HOME/experiments/"your workspace"
    source ../jobfile.sh
    ```
    