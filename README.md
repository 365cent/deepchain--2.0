# environment:
 - Python 3.6.4 |Anaconda
 - cupy      = 1.14.0
 - tensorflow = 1.7.0

# tools:
- sublime text3
- pycharm = 2018.1.3
- Ubuntu  = 16.04 or Windows10

# compiled language:
- Python = 3.6.4
# dataset:
- MNIST
        training:
          4 workers:
		         1.
		            4 workers: 13750 pictures for each one
		            share parameter : 6

		         2.
		            compared group:
					      group1 (using single data set): 13750 pictures
					      group2 (using full data set): 55000 pictures
		  10 workers:
		        1.
		            10 workers: 5500 pictures for each one

		        2.
		            compared group:
					      group1 (using single data set): 5500 pictures
					      group2 (using full data set): 55000 pictures

        validation: 5000 pictures
        test:       10000 pictures

# network:
         training model:

                Input ->  Conv layer1(5x5)->  Maxpool layer1(2x2)-> 
                Conv layer3(5x5)->  Maxpool layer3(2x2) ->
                Fully_connected layer1 ->Fully_connected layer1-> Output layer

                input image shape:          (1,1,28,28)(1: picture num,1: deepth,28: length ,28: width)
	            affer conv1 image shape:     (10,1,28,28)
                after max pool1 image shape: (10,1,14,14)
                affer conv1 image shape:     (20,10,14,14)
                after max pool1 image shape: (20,10,7,7)
  	            fully connected layer1:      (980,128)
  	            fully connected layer2:      (128,256)
                output layer:                (256,10)


# parameter config:
                  iteration :             1500
                  epoch :                 1
                  learning rate :         0.5
                  Worker_NUM :            4
                  mini_batch_size :       64
                  optimizer function:     stochastic gradient descent
                  conv layer1 :            W1 = (10,1,5,5)  b1 =(10,1)
                  conv layer2 :            W2 = (20,10,5,5) b2 =(20,1)
                  fully connected layer1 : W4 = (980,128)   b4 =(1,128)
                  fully connected layer2 : W5 = (128,256)   b5 =(1,256)
                  output layer :           W6 = (256,10)    b3 = (1,10）

# result:
    worker_num: 10
	    accuracy:
		    training(validation):
				worker1: 0.968000
				worker2: 0.969800
				worker3: 0.973400
				worker4: 0.972200
				worker5: 0.974200
				worker6: 0.969200
				worker7: 0.966800
				worker8: 0.971400
				worker9: 0.971400
				worker10:0.970200
		        compared groups:
						  group1 (using single data set) : 0.966000
						  group2 (using full data set)   : 0.975800
		    testing:
				worker1: 0.9677
				worker2: 0.9687
				worker3: 0.9701
				worker4: 0.9706
				worker5: 0.9703
				worker6: 0.9654
				worker7: 0.9658
				worker8: 0.9705
				worker9: 0.9728
				worker10: 0.9681
				compared groups :
						group1  (using single data set)  : 0.9644
						group2  (using full data set)    : 0.9762


	worker_num: 4
		accuracy:
		training(validation):
				worker1: 0.970800
				worker2: 0.969600
				worker3: 0.972000
				worker4: 0.973200
		        compared groups:
						  group1 (using single data set) : 0.963600
						  group2 (using full data set)   : 0.981800
		testing:
				worker1: 0.9674
				worker2: 0.9733
				worker3: 0.9710
				worker4: 0.9720
				compared groups :
						group1  (using single data set)  : 0.9621
						group2  (using full data set)    : 0.9837
# usage
In windows10 or ubuntu16.04 run :python ./run_mnist.py
