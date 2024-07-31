// Update category ID in posts
// Retreive all categories
const categories = db.categories.find({}).toArray();

// Create map of category names to their IDs
const categoryMap = {};
categories.forEach(category => {
	categoryMap[category.name] = category._id;
})

// Update posts with category ID
db.posts.find({}).forEach(post => {
	const categoryId = categoryMap[post.category];
	if(categoryId) {
		db.posts.updateOne({_id: post._id }, {$set: {category: categoryId}})
	}
});