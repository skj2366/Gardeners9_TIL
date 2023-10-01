# take()

'''kt
fun <T> Array<out T>.take(n: Int): List<T>
'''

Collection의 앞에서 부터 n 만큼 취해서 List로 반환


'''kt
(0..10).toList().take(5)
// [0, 1, 2, 3, 4]
'''

# takeLast()
'''kt
fun <T> Array<out T>.takeLast(n: Int): List<T> 
'''

Collection의 뒤에서부터 n만큼 취해서 List로 반환

'''kt
(0..10).toList().takeList(5)
// [10, 9, 8, 7, 6]
'''
