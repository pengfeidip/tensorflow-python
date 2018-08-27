改变了weights的初始化方法
base: tf.truncated_truncated_normal_initializer(stddev=1.0)
change: tf.truncated_truncated_normal_initializer(stddev=0.1)