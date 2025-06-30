# Dictionary mapping melanoma locations to ICD-10-CM codes
melanoma_icd10_map = {
    "lip": "C43.0",
    "eyelid": "C43.1",
    "ear": "C43.2",
    "face": "C43.3",
    "scalp": "C43.4",
    "neck": "C43.4",
    "trunk": "C43.5",
    "upper limb": "C43.6",
    "shoulder": "C43.6",
    "lower limb": "C43.7",
    "hip": "C43.7",
    "overlapping": "C43.8",
    "unspecified": "C43.9"
}

def get_melanoma_icd10(description: str) -> str:
    """Return ICD-10-CM code for melanoma based on anatomical site description."""
    description = description.lower()
    for key in melanoma_icd10_map:
        if key in description:
            return melanoma_icd10_map[key]
    return melanoma_icd10_map["unspecified"]  # Default if no match found

# Example usage
sample_descriptions = [
    "Melanoma on the upper back",
    "Melanoma of the scalp",
    "Skin cancer on the eyelid",
    "Melanoma, unspecified location"
]

for desc in sample_descriptions:
    code = get_melanoma_icd10(desc)
    print(f"{desc} -> ICD-10: {code}")
