# FirstLine
Project for university 
describe('testing Array.prototype.toList()', function() {
	var list = {
	head: 1,
	tail: {
		head: 2,
		tail: {
			head: 3,
			tail: undefined
		}
	}
}
	it('should not lose content', function() {
		Array.prototype.toList = function() {
	         const obj = {};
	         let prevObj = obj;
	         for(let i = 0; i < this.length; i++) {
	             prevObj.head = this[i];
	             if (i !== this.length - 1) {
	                 prevObj.tail = {}
	                 prevObj = prevObj.tail;
	             } else {
	                 prevObj.tail = undefined;
	             }
	         }
	         return obj;
	     }
assert.deepEqual([1,2,3].toList(), list) });
})
