### Solution

resource "aws_eip" "nautilus-eip" {
  tags = {
    Name = "nautilus-eip"
  }
}
