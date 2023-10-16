# RNA SEQUENCE ANALYZER

def count_bases(rna_sequence):
    base_count = {'A': 0, 'C': 0, 'G': 0, 'U': 0}
    
    for base in rna_sequence:
        if base in base_count:
            base_count[base] +=1
    
    return base_count

def gc_content(rna_sequence):
    gc_count = rna_sequence.count('G') + rna_sequence.count('C')
    total_bases = len(rna_sequence)
    gc_percentage = (gc_count / total_bases) * 100
    return gc_percentage

if __name__ == "__main__":
    sequence = input("Enter an RNA sequence: ").upper()
    
    base_counts = count_bases(sequence)
    gc_percent = gc_content(sequence)
    
    print("Base Counts:")
    for base, count in base_counts.items():
        print(f"{base}: {count}")
    
    print(f"GC Content: {gc_percent:.2f}%")
