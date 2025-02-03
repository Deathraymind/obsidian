- import torch
  
  # Check if ROCm (HIP) is available
  print("ROCm available:", torch.cuda.is_available())
  
  # Get GPU name
  if torch.cuda.is_available():
      print("GPU Name:", torch.cuda.get_device_name(0))
  
  # Try running a simple tensor operation on the GPU
  x = torch.tensor([1.0, 2.0, 3.0]).cuda()
  print("Tensor on GPU:", x)