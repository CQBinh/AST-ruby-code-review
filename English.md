# max/max_by: trả lại yếu tố lớn nhất

```ruby
def oldest_user(users)
  oldest = nil
  users.each do |user|
    oldest = user if oldest.nil? || user.age > oldest.age
  end
  oldet
end
```

```ruby
def oldest_user(users)
  users.max_by(&:age)
end
```

Nếu chỉ đơn thuần là số hoặc chuỗi kí tự thì dùng `numbers.max` là đủ. 
Trong trường hợp tìm yếu tố nhỏ nhất thì dùng `min`, `min_by`. 

# each_with_object: vòng lặp với đối tượng tương ứng

```ruby
def admin_names(users)
  ret = []
  users.each do |user|
    ret << user.name if user.admin?
  end
  ret
end
```

```ruby
def admin_names(users)
  users.each_with_object([]) do |user, names|
    names << user.name if user.admin?
  end
end
```

Ngoài ra còn cách viết ngắn hơn nhưng sẽ khá khó đọc với người mới `users.select(&:admin?).map(&:name)`. 