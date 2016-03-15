def manage_load(arr)
  t = 0
  if arr.uniq.size == 1
    puts t
    return
  elsif arr.inject(:+) % arr.size != 0
    puts "Load cannot be balanced equally"
    return
  end
  balanced_load = arr.inject(:+)/arr.size
  (arr.min+1..balanced_load).each do |bal_ld|
  begin
    arr.each_with_index do |load, indx|
      distribute_load(arr,indx, bal_ld) if load > bal_ld
    end
    t += 1
    #puts "Server loads at time t=#{t}"
    #puts arr.join(",")
  end while arr.any? {|ser_ld| ser_ld < bal_ld}
  
  end
  puts t
end
  
def distribute_load(a, i, bal)
  l = a.length
  j,k= i,i
  while (a[j-1] != (bal-1) and j>1)
      j-=1
  end
  if a[j-1] == bal-1 and a[i] >bal and i!=0
      a[j-1]+=1
      a[i]-=1
  end
  while (a[k+1] != bal-1 and k<l)
      k+=1
  end
  if a[k+1] == bal-1 and a[i]>bal
      a[k+1]+=1
      a[i]-=1
  end 
end

    
puts "Enter the Input"
input=gets.split(",")
invalid_ld = 0
input.each do |ld|
  unless (Integer(ld) != nil rescue false) and ld.to_i >= 0
    invalid_ld += 1
    puts "Please Enter the valid input"
    break
  end
end
manage_load(input.map(&:to_i)) if invalid_ld == 0