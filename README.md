# 5400-hw3
# Decision options encoded numerically
storage <- 0:2 # Local Server, On-Device, Cloud
biometrics <- 0:2 # Eye Scan, Thumbprint, Face Recognition
control_hub <- 0:1 # Mobile App, Home Tablet
# Simplifying Devices, Machine Learning, Control Options, Device Placement, and Security Levels for demonstration
devices <- 0:2 # Simplified as 3 options
machine_learning <- 0:2 # Video Feed Analysis, Human Behavior Analysis, Human Identification Analysis
control_options <- 0:2 # Simplified as 3 options
device_placement <- 0:2 # Simplified locations
security_levels <- 0:2 # Low, Medium, High

set.seed(123) # Ensure reproducibility
n <- 100 # Number of architectures

# Randomly sample decisions to generate architectures
random_architectures <- data.frame(
  storage = sample(storage, n, replace = TRUE),
  biometrics = sample(biometrics, n, replace = TRUE),
  control_hub = sample(control_hub, n, replace = TRUE),
  devices = sample(devices, n, replace = TRUE),
  machine_learning = sample(machine_learning, n, replace = TRUE),
  control_options = sample(control_options, n, replace = TRUE),
  device_placement = sample(device_placement, n, replace = TRUE),
  security_levels = sample(security_levels, n, replace = TRUE)
)
# Display the first 5 architectures to check
head(random_architectures, 5)
# Count occurrences of each option for a decision to check uniformity
table(random_architectures$storage) # Example for 'storage'

decision_names <- names(random_architectures)
for (decision in decision_names) {
  cat("Distribution for", decision, ":\n")
  print(table(random_architectures[[decision]]))
  cat("\n")
}
