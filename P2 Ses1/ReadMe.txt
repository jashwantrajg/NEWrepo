I was unable to provide the training data as a got an error which im unable to solve . Pls do let me know the mistake was.



<_io.TextIOWrapper name='C:\\Users\\jashw\\Desktop\\glove\\glove.6B.100d.txt' mode='r' encoding='utf-8'>
Found 400000 word vectors.
[[0. 0. 0. ... 0. 0. 0.]
 [0. 0. 0. ... 0. 0. 0.]
 [0. 0. 0. ... 0. 0. 0.]
 ...
 [0. 0. 0. ... 0. 0. 0.]
 [0. 0. 0. ... 0. 0. 0.]
 [0. 0. 0. ... 0. 0. 0.]]
Model: "sequential_7"
_________________________________________________________________
Layer (type)                 Output Shape              Param #   
=================================================================
embedding_7 (Embedding)      (None, 100, 100)          1000000   
_________________________________________________________________
flatten_7 (Flatten)          (None, 10000)             0         
_________________________________________________________________
dense_25 (Dense)             (None, 1)                 10001     
=================================================================
Total params: 1,010,001
Trainable params: 1,010,001
Non-trainable params: 0
_________________________________________________________________

---------------------------------------------------------------------------
ValueError                                Traceback (most recent call last)
<ipython-input-13-e7c3a9104f15> in <module>
     40 
     41 model.compile(optimizer='adam',loss='binary_crossentropy',metrics=['acc'])
---> 42 history = model.fit(x_train, y_train, epochs = 10,batch_size=32,validation_data=(x_val, y_val))
     43 model.save_weights('pre_trained_glove_model.h5')

C:\anaconda\lib\site-packages\keras\engine\training.py in fit(self, x, y, batch_size, epochs, verbose, callbacks, validation_split, validation_data, shuffle, class_weight, sample_weight, initial_epoch, steps_per_epoch, validation_steps, validation_freq, max_queue_size, workers, use_multiprocessing, **kwargs)
   1152             sample_weight=sample_weight,
   1153             class_weight=class_weight,
-> 1154             batch_size=batch_size)
   1155 
   1156         # Prepare validation data.

C:\anaconda\lib\site-packages\keras\engine\training.py in _standardize_user_data(self, x, y, sample_weight, class_weight, check_array_lengths, batch_size)
    619                 feed_output_shapes,
    620                 check_batch_axis=False,  # Don't enforce the batch size.
--> 621                 exception_prefix='target')
    622 
    623             # Generate sample-wise weight values given the `sample_weight` and

C:\anaconda\lib\site-packages\keras\engine\training_utils.py in standardize_input_data(data, names, shapes, check_batch_axis, exception_prefix)
    143                             ': expected ' + names[i] + ' to have shape ' +
    144                             str(shape) + ' but got array with shape ' +
--> 145                             str(data_shape))
    146     return data
    147 

ValueError: Error when checking target: expected dense_25 to have shape (1,) but got array with shape (100,)

